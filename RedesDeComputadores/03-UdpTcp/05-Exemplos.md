### **1. Streaming Sob Demanda (Ex.: Netflix, YouTube)**
#### **Tipo de Comunicação**  
✅ **Sem conexão** (geralmente UDP ou HTTP/3 QUIC) + **Confirmação opcional** (depende do protocolo).  

#### **Por quê?**  
- **Prioridade: Velocidade e baixa latência**.  
  - Se um pacote de vídeo se perder, **não há retransmissão** (o player simplesmente pula o frame ou usa técnicas de buffering).  
  - Protocolos como **UDP** (usado em RTP/RTSP para streaming) ou **QUIC** (HTTP/3, que roda sobre UDP mas adiciona confirmações seletivas) são comuns.  
- **Não há handshake prolongado** (conexão contínua), mas alguns protocolos podem enviar **ACKs esporádicos** para ajustar a taxa de transferência.  

#### **Exemplo Técnico**  
- Se você está assistindo um vídeo e a rede fica instável:  
  - O player **não para** para retransmitir pacotes perdidos (a menos que o buffer acabe).  
  - Pode haver **confirmações apenas para controle de fluxo** (ex.: "diminui a velocidade, estou congestionado!").  

---

### **2. Download de Arquivos (Ex.: FTP, HTTP, Torrent)**
#### **Tipo de Comunicação**  
✅ **Com conexão** (TCP na maioria dos casos) + **Com confirmação obrigatória**.  

#### **Por quê?**  
- **Prioridade: Integridade dos dados**.  
  - Se um pacote do arquivo se corromper ou se perder, **o TCP exige retransmissão**.  
  - Handshake inicial (SYN, SYN-ACK, ACK) + ACKs para cada bloco de dados.  
- **Exemplo**:  
  - Se você baixa um arquivo .zip via HTTP (TCP), o navegador **só aceita o arquivo completo e íntegro**.  

---

### **3. Comparação Direta**
| **Aplicação**         | **Tipo de Comunicação**       | **Conexão?** | **Confirmação?** | **Protocolo Típico** |  
|-----------------------|-------------------------------|--------------|------------------|----------------------|  
| **Streaming (Vídeo)** | Dados em tempo real           | ❌ (UDP) ou ✅ leve (QUIC) | ❌ (UDP puro) ou ✅ seletiva (QUIC) | UDP, RTP, QUIC |  
| **Download**          | Transferência confiável       | ✅ (TCP)      | ✅ (ACKs obrigatórios) | TCP, HTTP, FTP |  

---

### **4. Casos Especiais e Exceções**  
- **Streaming Adaptativo (Ex.: HLS, DASH)**:  
  - Usa HTTP/TCP (tecnicamente "com conexão"), mas **não retransmite frames perdidos** (apenas ajusta a qualidade do vídeo).  
  - **Meio-termo**: TCP garante a entrega dos segmentos de vídeo, mas se um pacote se perder, o player **prioriza continuar a reprodução** em vez de esperar retransmissão.  

- **Torrent (P2P)**:  
  - Usa TCP para downloads normais, mas **pedaços do arquivo podem ser verificados** (confirmação indireta via hash).  

---

### **5. Conclusão**  
- **Streaming de vídeo**:  
  - **Sem conexão persistente** (UDP) ou **conexão leve** (QUIC).  
  - **Confirmação apenas para controle** (não para retransmissão de frames).  
- **Download de arquivos**:  
  - **Sempre com conexão (TCP) e confirmação rigorosa** (ACKs + retransmissão).  

**TL;DR:**  
- **Vídeo sob demanda** = "Entrega rápida, mesmo que perca alguns pacotes." → **UDP/QUIC**.  
- **Download** = "Quero TUDO, sem erros!" → **TCP**.  

