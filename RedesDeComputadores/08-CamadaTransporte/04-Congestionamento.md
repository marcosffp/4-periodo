### **TCP e Controle de Congestionamento**

**Ideia Central: O TCP é um protocolo "educado" que não quer entupir a internet. Ele sempre pergunta: "A rede está aguentando o tranco?" e ajusta sua velocidade com base na resposta.**

#### **1. A Base de Tudo: O "Diálogo" entre Cliente e Servidor**

Antes de qualquer regra, você precisa imaginar a conexão como uma conversa:

*   **Emissor (Quem envia dados):** "Olha, estou te mandando os bytes de número 8001 a 8100."
*   **Receptor (Quem recebe):** "Beleza, recebi tudo até o byte 8100. Pode mandar a partir do 8101!" (Isso é um **ACK**).

**Glossário Mínimo pra Não Se Perder:**
*   **ACK:** É um "recibo" que diz "recebi tudo até aqui, pode mandar o próximo".
*   **Número de Sequência:** É o "CPF" de cada byte enviado.
*   **cwnd (Janela de Congestionamento):** É a quantidade de dados que o emissor pode "jogar na rede" sem ter recebido um recibo. É o **pé no acelerador** da conexão.
*   **ssthresh:** Um limite de velocidade. Abaixo dele, o TCP acelera rápido. Acima dele, ele acelera com cuidado.
*   **Timeout:** Quando o emissor manda um pacote e não recebe o "recibo" (ACK) depois de muito tempo. Algo grave aconteceu.

---

#### **2. A História de uma Perda de Pacote (A Linha de Raciocínio)**

Vamos acompanhar o que acontece quando um pacote se perde. Esta é a **história completa** que faltava no resumo anterior.

**Cenário Inicial:**
*   Emissor envia 4 pacotes: **Pacote 1 (Bytes 8001)**, **Pacote 2 (8101)**, **Pacote 3 (8201)**, **Pacote 4 (8301)**.

**O Problema:**
1.  **O Pacote 2 (8101) se perde no caminho.** Os pacotes 1, 3 e 4 chegam.

**A Reação do Receptor (Quem Recebe):**
2.  **Pacote 1 chega (8001):** "Ótimo! Recebi até 8100. **ACK 8101**." (Tudo normal).
3.  **Pacote 3 chega (8201):** "Opa, estranho. Eu esperava o 8101, mas chegou o 8201. O 8101 deve ter se perdido. Vou pedir de novo: **ACK 8101**." (Este é um **ACK Duplicado**. É como gritar "Cadê o 8101?").
4.  **Pacote 4 chega (8301):** "Putz, chegou outro, mas ainda não é o 8101! **ACK 8101** de novo!" (Segundo ACK duplicado).

**A Reação do Emissor (Quem Envia):**
5.  Ele recebe o primeiro ACK 8101 (normal). Depois, recebe **mais três ACKs 8101 seguidos** (duplicados).
6.  **"Ahá!" – pensa o emissor – "Recebi TRÊS recibos duplicados pedindo a mesma coisa. Isso é um sinal claro de que o Pacote 2 (8101) se perdeu. Não preciso esperar o tempo esgotar (timeout), vou retransmitir AGORA!"**. Essa reação inteligente se chama **Fast Retransmit (Retransmissão Rápida)**.
7.  Emissor **retransmite o Pacote 2 (8101)**.

**O Final Feliz:**
8.  O Pacote 2 (8101) finalmente chega. O receptor, que já tinha os pacotes 3 e 4, fica feliz da vida. Ele agora tem todos os bytes em ordem até o 8400. Ele manda um **ACK 8401**, avisando: "Perfeito! Agora tenho tudo até 8400, pode mandar o próximo!"
9.  A conversa volta ao normal.

**Resumo da História:** O TCP é esperto. Em vez de travar e esperar um tempão (timeout) quando um pacote some, ele usa os "ACKs duplicados" como um grito de ajuda para retransmitir rapidamente.

---

#### **3. Controle de Congestionamento: Como o TCP Pisa e Solta o Acelerador**

Agora, a parte mais importante: **como a velocidade é controlada**. Tudo gira em torno da **cwnd** (a janela de congestionamento).

O TCP tem duas fases principais de direção:

**Fase 1: Partida Lenta (Slow Start) - "Vamos com Calma"**
*   **Quando:** No início da conexão ou após uma falha grave (timeout).
*   **O que faz:** A `cwnd` dobra de tamanho a cada "ida e volta" (RTT) dos pacotes. É um crescimento **exponencial** (1, 2, 4, 8, 16...).
*   **Objetivo:** Descobrir rapidamente a capacidade da rede.
*   **Parada:** Quando a `cwnd` atinge o limite `ssthresh` ou quando ocorre uma perda de pacote.

**Fase 2: Evitação de Congestionamento - "Pé no Freio Motor"**
*   **Quando:** A `cwnd` está alta, perto do limite da rede.
*   **O que faz:** A `cwnd` aumenta apenas de **1 em 1 segmento** por RTT. É um crescimento **linear** e conservador (17, 18, 19...).
*   **Objetivo:** Aproximar-se da capacidade máxima da rede sem entupi-la.

---

#### **4. O que Acontece Quando Dá Errado? Tahoe vs Reno**

A diferença crucial está em **como eles reagem a uma perda**.

**TCP Tahoe (O Conservador)**
*   **Perdeu um pacote (tanto faz se foi timeout ou 3 ACKs duplicados)?**
    1.  **Pisa fundo no freio:** `cwnd = 1` (Volta para a estaca zero).
    2.  `ssthresh = cwnd / 2` (Abaixa o limite de velocidade).
    3.  Reinicia a **Partida Lenta**.
*   **Problema:** É muito brusco. Uma perdinha pequena faz a conexão voltar a engatinhar.

**TCP Reno (O Esperto)**
*   **Se for uma falha GRAVE (Timeout):** Faz igual ao Tahoe (`cwnd = 1`).
*   **Se for uma perda PEQUENA (3 ACKs Duplicados):** Ele é mais esperto!
    1.  `ssthresh = cwnd / 2`
    2.  `cwnd = ssthresh` (Só reduz pela metade, não zera!)
    3.  Entra em **Recuperação Rápida (Fast Recovery)**, onde já pode enviar novos pacotes enquanto espera a confirmação do pacote retransmitido.
*   **Vantagem:** É muito mais eficiente para redes modernas, onde perdas isoladas são comuns. A conexão não "cai de pau" a cada problema.

---

### **Tabela-Resumo: "O que eu faço quando..."**

| O que Aconteceu? | O que o TCP Faz? | Explicação para Leigos |
| :--- | :--- | :--- |
| **Recebo um ACK novo** | Avanço a janela e envio novos dados. | "O recibo chegou, posso mandar mais mercadoria." |
| **Recebo um pacote fora de ordem** | Envio um ACK duplicado. | "Grito 'Cadê o pacote que faltou?'." |
| **Recebo 3 ACKs duplicados** | **Fast Retransmit:** Retransmito o pacote perdido NA HORA. | "Três gritos? Retransmito agora sem esperar!" |
| **Ocorre um Timeout** | Retransmito e **reduzo MUITO a velocidade (`cwnd`)**. | "A rede travou totalmente. Melhor recomeçar devagar." |
| **Estou na Partida Lenta** | Dobro minha velocidade (`cwnd`) a cada ida e volta. | "Piso fundo no acelerador com cuidado." |
| **Estou na Evitação de Congestionamento** | Aumento a velocidade (`cwnd`) de 1 em 1 a cada ida e volta. | "Pé no freio motor, aumentando a velocidade bem devagar." |
