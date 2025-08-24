### **Com Confirmação vs Sem Confirmação**  

## **1. Comunicação **COM CONFIRMAÇÃO (ACK)****  
### **O que define?**  
- **Cada pacote enviado exige uma resposta** (ACK = *acknowledgment*).  
- Se o remetente **não receber um ACK**, ele reenvia o pacote.  
- Pode ser usado **tanto em conexões orientadas (TCP) quanto não orientadas (alguns protocolos especiais)**.  

### **Como Funciona?**  
1️⃣ **Remetente envia Pacote #1**  
2️⃣ **Destinatário recebe Pacote #1 → Envia ACK** ("Recebi!")  
3️⃣ **Remetente recebe ACK → Envia Pacote #2**  
4️⃣ **Se ACK não chegar em um tempo limite → Remetente reenvia Pacote #1**  

### **Exemplo Prático**  
> **WhatsApp com "confirmação de leitura"**:  
> - Você manda mensagem (✅ enviado).  
> - O destinatário recebe (✅ entregue).  
> - O destinatário abre (✅ lido).  
> - Se não houver "lido", você pode perguntar: "Viu minha mensagem?" (retransmissão implícita).  

---

## **2. Comunicação **SEM CONFIRMAÇÃO****  
### **O que define?**  
- **Nenhum ACK é enviado** – o remetente dispara os dados e não espera resposta.  
- **Não há retransmissão automática** – se perder, perdeu.  
- Usado quando **velocidade > confiabilidade**.  

### **Como Funciona?**  
1️⃣ **Remetente envia Pacote #1**  
2️⃣ **Destinatário recebe (ou não) – Nenhum ACK é enviado**  
3️⃣ **Remetente já envia Pacote #2, sem saber se #1 chegou**  

### **Exemplo Prático**  
> **Transmissão ao vivo no YouTube**:  
> - Os pacotes de vídeo são enviados **sem parar**.  
> - Se alguns frames se perderem, o vídeo continua (ninguém pede reenvio).  
> - **Prioridade: fluidez, não perfeição**.  

---

## **3. Comparação Direta**  
| **Critério**          | **Com Confirmação (ACK)**          | **Sem Confirmação**               |  
|-----------------------|------------------------------------|-----------------------------------|  
| **Feedback**          | ✅ (cada pacote é confirmado)      | ❌ (nenhuma resposta)             |  
| **Retransmissão**     | ✅ (se faltar ACK, reenvia)        | ❌ (não há retentativa)           |  
| **Confiabilidade**    | Alta                               | Baixa                             |  
| **Velocidade**        | Mais lento (espera por ACKs)       | Mais rápido (envio contínuo)      |  
| **Uso típico**        | Download de arquivos, emails       | Streaming, VoIP, jogos online     |  

---

## **4. Casos Híbridos**  
Alguns sistemas usam **confirmação parcial**:  
- **ACKs periódicos** (ex.: a cada 10 pacotes).  
- **ACKs seletivos** (só confirma pacotes críticos).  

---

### **TL;DR**  
- **Com Confirmação (ACK)**: "Cadê meu OK?" → Ideal para **dados críticos**.  
- **Sem Confirmação**: "Segue o baile" → Ideal para **tempo real**.  
