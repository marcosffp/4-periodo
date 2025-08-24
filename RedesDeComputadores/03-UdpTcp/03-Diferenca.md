### 🔗 **Conexão (Connection-Oriented)**
- **O que é?**  
  Um canal lógico estabelecido **antes** da troca de dados.  
- **Características:**  
  - Requer **handshake inicial** (ex.: TCP usa SYN, SYN-ACK, ACK).  
  - Mantém um **estado da sessão** (ex.: controle de fluxo, sequência de pacotes).  
  - Encerramento formal (ex.: FIN no TCP).  
- **Objetivo:**  
  Garantir que **ambos os lados estão sincronizados** para uma comunicação ordenada.  

### ✔️ **Confirmação (Acknowledgement - ACK)**
- **O que é?**  
  Um **feedback imediato** para cada pacote recebido.  
- **Características:**  
  - Pode existir **com ou sem conexão**.  
  - **Retransmite** se o ACK não chegar (em sistemas confiáveis).  
  - Não implica em estado de sessão (pode ser usado em protocolos sem conexão).  
- **Objetivo:**  
  Garantir que **cada pacote individual** foi entregue.  

### 📌 **Diferença Chave**
| **Conexão**                          | **Confirmação**                     |
|--------------------------------------|-------------------------------------|
| Estabelece um **canal lógico duradouro**. | É um **mecanismo pontual** por pacote. |
| Envolve **handshake e encerramento**. | Só precisa de um **ACK** (pode ser único). |
| Exemplo: **TCP**.                    | Exemplo: **TCP usa ACKs**, mas **UDP não** (embora alguns apps adicionem ACKs em cima do UDP). |

### 🌍 **Analogia**
- **Conexão** = Fazer uma **ligação telefônica** (você estabelece a chamada, conversa e depois desliga).  
- **Confirmação** = Pedir **"Tá me ouvindo?"** durante a ligação (verificação pontual).  

### ⚡ **Resumo**
- **Conexão** = **"Vamos combinar um canal antes de conversar?"**  
- **Confirmação** = **"Você recebeu o que eu acabei de dizer?"**  

Um protocolo **pode ter ambos** (ex.: TCP), **nenhum** (ex.: UDP puro), ou **apenas confirmação** (ex.: protocolos personalizados sobre UDP).  

