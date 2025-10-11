# 📚 Camada de Transporte

## 1. O que é a Camada de Transporte?
A Camada de Transporte é como um **serviço de entrega confiável** entre dois programas que estão se comunicando pela rede, mesmo que a rede em si não seja confiável. Ela garante que os dados saiam de um programa no computador de origem e cheguem corretamente ao programa de destino, sem que o usuário precise se preocupar com os detalhes da rede.

> **Exemplo**: É como enviar uma carta com aviso de recebimento: você tem certeza de que o destinatário recebeu, mesmo que o carteiro possa ter enfrentado problemas no caminho.

---

## 2. Serviços da Camada de Transporte
### Orientado à Conexão vs. Não Orientado à Conexão
- **Orientado à Conexão**: Antes de enviar dados, é estabelecida uma conexão (como uma ligação telefônica). Exemplo: TCP.
- **Não Orientado à Conexão**: Os dados são enviados sem estabelecimento prévio (como um telegrama). Exemplo: UDP.

---

## 3. Primitivas de Serviço (Funções Básicas)
Essas são as operações que os programas usam para se comunicar via rede:

| Primitiva | O que faz |
|-----------|-----------|
| `Socket` | Cria um ponto de comunicação. |
| `Bind` | Associa um endereço (porta) ao socket. |
| `Listen` | Anuncia que está pronto para receber conexões. |
| `Accept` | Aceita uma conexão de um cliente. |
| `Connect` | Tenta conectar a um servidor. |
| `Send` | Envia dados. |
| `Receive` | Recebe dados. |
| `Close` | Encerra a conexão. |

> **Exemplo**: Um servidor web usa `listen` e `accept` para receber pedidos de navegadores.

---

## 4. Diferenças entre Camada de Transporte e Enlace
- A camada de enlace cuida da comunicação entre **máquinas vizinhas** (ex: roteadores conectados).
- A camada de transporte cuida da comunicação entre **processos em máquinas diferentes**, lidando com múltiplos destinos e atrasos na rede.

---

## 5. Endereçamento e Portas
Cada programa em comunicação usa um **número de porta** para ser identificado.

- **Portas bem conhecidas (0–1023)**: Serviços padrão (ex: HTTP na porta 80).
- **Portas registradas (1024–49151)**: Serviços menos comuns.
- **Portas dinâmicas (49152–65535)**: Uso temporário.

> **Exemplo**: O servidor de dia e hora (daytime) usa a porta 13.

---

## 6. Multiplexação e Encapsulamento
- **Multiplexação**: Vários programas podem usar a mesma conexão de rede ao mesmo tempo.
- **Encapsulamento**: Os dados da aplicação são empacotados com um cabeçalho da camada de transporte (e depois com cabeçalhos de rede e enlace).

> **Analogia**: É como colocar uma carta em um envelope (transporte), que vai dentro de outro envelope (rede), que vai dentro de uma caixa (enlace).

---

## 7. Controle de Fluxo e Erros
- **Controle de fluxo**: Evita que o remetente envie dados rápido demais para o receptor.
- **Controle de erros**: Detecta e corrige dados corrompidos ou perdidos.

---

## 8. Protocolos de Janela Deslizante
São usados para melhorar a eficiência e confiabilidade.

### a) Stop-and-Wait
- Envia **um quadro por vez** e espera a confirmação (ACK) antes de enviar o próximo.
- **Problema**: Muito lento se a rede for lenta.

### b) Go-Back-N
- O transmissor envia vários quadros de uma vez (janela).
- Se um quadro se perde, **retransmite todos a partir do perdido**.
- **Vantagem**: Mais rápido que Stop-and-Wait.
- **Desvantagem**: Gasta banda retransmitindo quadros já recebidos.

### c) Selective Repeat
- O receptor armazena quadros corretos mesmo que cheguem fora de ordem.
- Apenas o quadro perdido é retransmitido.
- **Vantagem**: Mais eficiente que Go-Back-N.
- **Desvantagem**: Requer mais memória no receptor.

---

## 9. ARQ, ACK, Timeout e Piggybacking
- **ARQ (Automatic Repeat Request)**: Repetição automática de quadros perdidos.
- **ACK (Acknowledgement)**: Confirmação de recebimento.
- **Timeout**: Tempo de espera por um ACK antes de reenviar.
- **Piggybacking**: O ACK é enviado junto com dados, economizando transmissões.

---

## 10. Eficiência e Pipelining
### Exemplo Numérico:
- Canal de satélite: 50 kbps, RTT = 500 ms, quadro = 1000 bits.
- Tempo para enviar 1 quadro = 20 ms.
- Tempo total para enviar e receber ACK = 520 ms.
- Eficiência sem pipelining = apenas **4%**!

### Pipelining:
- Permite enviar vários quadros antes de esperar ACKs.
- No exemplo: janela de 26 quadros → eficiência próxima de 100%.

---

## 11. UDP (User Datagram Protocol)
- **Serviço não confiável e sem conexão**.
- **Cabeçalho pequeno** (8 bytes).
- **Não controla fluxo nem erro**.
- **Usos**: DNS, vídeo streaming, onde velocidade é mais importante que confiabilidade.

### Formato do UDP:
```
| Porta Origem (16 bits) | Porta Destino (16 bits) |
| Comprimento (16 bits)  | Checksum (16 bits)     |
| Dados...                                           |
```

> **Exemplo**: É como mandar um cartão postal: rápido, mas sem garantia de entrega.

---

## ✅ Resumo Final em 5 Linhas

1. A Camada de Transporte garante comunicação confiável entre programas, mesmo em redes instáveis.
2. Oferece serviços com e sem conexão, usando portas para identificar aplicações.
3. Protocolos como TCP usam janelas deslizantes e confirmações para controle de fluxo e erro.
4. Técnicas como pipelining e retransmissão seletiva melhoram a eficiência.
5. UDP é uma alternativa simples e rápida, mas sem confiabilidade, ideal para aplicações que toleram perdas.


---


## 1. O que é o TCP?
O **TCP (Transmission Control Protocol)** é um protocolo da camada de transporte que garante a comunicação **confiável** e **ordenada** entre dois processos em redes de computadores. Pense nele como uma **conversa telefônica**: antes de trocar informações, é preciso estabelecer a ligação (conexão), garantir que a outra parte está ouvindo (confirmações) e encerrar a chamada de forma organizada.

**Por que é orientado à conexão?**  
Porque, antes de trocar dados, o cliente e o servidor realizam um "aperto de mãos" (handshake) para estabelecer a conexão. Isso garante que ambos estejam prontos para a comunicação.

**Por que é confiável?**  
Porque o TCP usa confirmações (ACKs) e retransmissões para assegurar que todos os dados enviados cheguem corretamente ao destino.

---

## 2. Serviços e Funcionamento Básico
- **Comunicação Processo-a-Processo**: Identificada por **portas** (ex.: porta 80 para HTTP).
- **Fluxo de Bytes**: Os dados são tratados como uma sequência contínua de bytes.
- **Buffers de Envio e Recepção**: Armazenam temporariamente os dados antes do envio e após o recebimento.
- **Full-Duplex**: Ambos os lados podem enviar e receber dados ao mesmo tempo.
- **Segmentação**: Os dados são divididos em **segmentos** que cabem em quadros de rede (limitação pelo **MTU – Unidade Máxima de Transmissão**, ex.: 1500 bytes em Ethernet).

---

## 3. Cabeçalho TCP (Explicação dos Campos)
O cabeçalho tem entre **20 e 60 bytes**. Os principais campos são:

| Campo | Função |
|--------|---------|
| **Porta de Origem e Destino** | Identificam os processos em cada máquina. |
| **Número de Sequência** | Identifica a posição do primeiro byte do segmento no fluxo total. |
| **Número de Confirmação (ACK)** | Indica o próximo byte que o receptor espera receber. |
| **Flags (SYN, ACK, FIN, RST, PSH, URG)** | Controlam o estado da conexão e o tratamento dos dados. |
| **Tamanho da Janela** | Indica quantos bytes o receptor ainda pode receber (controle de fluxo). |
| **URG** | Dados urgentes devem ser processados imediatamente. |
| **PSH** | Força a entrega imediata dos dados ao processo, sem armazenar no buffer. |
| **RST** | Reinicia a conexão em caso de erro. |
| **SYN** | Inicia uma conexão. |
| **FIN** | Finaliza uma conexão. |
| **CWR/ECE** | Usados para controle de congestionamento. |

---

## 4. Estabelecimento e Encerramento de Conexão

### Three-Way Handshake (Estabelecimento):
1. **Cliente → Servidor**: SYN (solicitação de conexão)
2. **Servidor → Cliente**: SYN + ACK (confirma e também inicia)
3. **Cliente → Servidor**: ACK (confirma o SYN do servidor)

✅ Conexão estabelecida!

### Encerramento (Four-Way Handshake):
1. **Cliente → Servidor**: FIN (não tenho mais dados)
2. **Servidor → Cliente**: ACK (confirmo)
3. **Servidor → Cliente**: FIN (também não tenho mais dados)
4. **Cliente → Servidor**: ACK (confirmo)

✅ Conexão encerrada!

---

## 5. Controle de Fluxo: Janelas Deslizantes
O TCP usa um sistema de **janela deslizante** para controlar o fluxo de dados e evitar sobrecarregar o receptor.

- **Janela de Envio**: Mostra quais bytes já foram enviados, confirmados ou ainda podem ser enviados.
- **Janela de Recepção**: Mostra quais bytes já foram recebidos, consumidos ou ainda podem ser recebidos.

**Exemplo**:  
Se o receptor avisa `Window Size = 0`, significa que seu buffer está cheio e o transmissor deve parar de enviar até que a janela seja liberada.

---

## 6. Confirmações (ACKs) e Retransmissões

### Confirmação Cumulativa (ACK):
O receptor confirma o **próximo byte esperado**. Exemplo: Se recebeu os bytes 1-1000, envia `ACK = 1001`.

### Confirmação Seletiva (SACK):
Informa quais blocos de bytes foram recebidos fora de ordem, permitindo retransmissões mais eficientes.

### Regras de Confirmação (Resumo):
1. Sempre que enviar dados, inclua um ACK.
2. Atrase ACKs se possível para reduzir tráfego.
3. Confirme imediatamente se chegar um segmento em ordem.
4. Confirme imediatamente se chegar um segmento fora de ordem.
5. Confirme quando um segmento faltante for recebido.
6. Descarte duplicatas, mas confirme o próximo esperado.

---

## 7. Controle de Congestionamento
O TCP ajusta a taxa de transmissão para evitar congestionar a rede.

### Partida Lenta (Slow Start):
A janela de congestionamento (`cwnd`) começa pequena e **dobra** a cada RTT (tempo de ida e volta) até atingir um limiar.

### Aumento Aditivo (AIMD):
Após o limiar, a janela cresce **linearmente** (+1 a cada RTT).

### TCP Tahoe vs. Reno:
- **Tahoe**: Ao detectar perda (timeout ou 3 ACKs duplicados), volta à partida lenta.
- **Reno**: Se for por 3 ACKs duplicados, faz **retransmissão rápida** e reduz a janela pela metade, sem voltar ao início.

---

## 8. Algoritmo de Nagle
Evita envio excessivo de pacotes pequenos.  
**Funcionamento**:  
- O primeiro byte é enviado imediatamente.  
- Os demais bytes são acumulados até que o ACK do primeiro chegue.  
- Então, todos os bytes acumulados são enviados de uma vez.

**Exceção**: Aplicações interativas (como movimento do mouse) desativam esse algoritmo.

---

## 📌 Resumo Final em 5 Linhas

1. O TCP é um protocolo **confiável** e **orientado à conexão**.
2. Usa **three-way handshake** para estabelecer e **four-way handshake** para encerrar conexões.
3. Controla o fluxo com **janelas deslizantes** e confirmações (**ACKs**).
4. Retransmite dados perdidos e ajusta a velocidade com **controle de congestionamento**.
5. Garante que os dados cheguem **ordenados**, **sem erros** e **sem sobrecarregar** a rede.
