### **Orientado a Conexão vs Sem Conexão**  

## **1. Comunicação **COM CONEXÃO****  
### **O que define?**  
- **Estabelece um canal lógico** antes de transmitir dados.  
- **Confirmação a cada passo** (handshake, acknowledgments).  
- **Controle de fluxo e erro** (retransmissão se perder pacotes).  
- **Encerramento formal** da conexão.  

### **Etapas (3 Fases)**
#### **1️⃣ Estabelecimento da Conexão (Handshake)**  
- **Passo 1 (Cliente → Servidor):** "Olá, posso iniciar uma conexão?"  
- **Passo 2 (Servidor → Cliente):** "Sim, pode. Aqui estão minhas condições."  
- **Passo 3 (Cliente → Servidor):** "OK, vamos começar!"  
👉 **Só depois disso** os dados são transmitidos.  

#### **2️⃣ Transferência de Dados**  
- **Cada pacote enviado é confirmado** (ACK).  
- Se um pacote se perder, **há retransmissão**.  
- **Controle de fluxo**: Ajusta velocidade pra não sobrecarregar o receptor.  

#### **3️⃣ Encerramento da Conexão**  
- **Passo 1 (Cliente → Servidor):** "Quero encerrar."  
- **Passo 2 (Servidor → Cliente):** "OK, encerrando."  
- **Passo 3 (Cliente → Servidor):** "Conexão finalizada."  

### **Exemplo do Mundo Real**  
> Imagine uma **ligação telefônica**:  
> 1. Você disca e espera o outro atender **(handshake)**.  
> 2. Conversa e confirma se o outro entendeu ("Tá me ouvindo?") **(ACKs)**.  
> 3. Ao final, diz "Tchau" antes de desligar **(encerramento)**.  

---

## **2. Comunicação **SEM CONEXÃO****  
### **O que define?**  
- **Não há handshake** – os dados são enviados imediatamente.  
- **Não há confirmação (ACKs)** ou retransmissão.  
- **Não há encerramento formal**.  
- **Cada pacote é independente** (não há "sessão").  

### **Etapas (1 Fase Só)**  
#### **1️⃣ Envio Direto**  
- A origem **joga os dados na rede** sem aviso prévio.  
- O destino **recebe (ou não)** – sem feedback.  
- Se um pacote se perder, **ninguém se importa**.  

### **Exemplo do Mundo Real**  
> Imagine **enviar cartas pelo correio sem aviso prévio**:  
> - Você **não sabe** se a carta chegou.  
> - Se perder, **não há reenvio automático**.  
> - Não precisa avisar que acabou de enviar.  

---

## **3. Comparação Direta**  
| **Critério**          | **Com Conexão**                     | **Sem Conexão**                   |  
|-----------------------|-------------------------------------|-----------------------------------|  
| **Handshake**         | ✅ (3 etapas)                       | ❌ (envio direto)                 |  
| **Confirmação (ACK)** | ✅ (cada pacote é confirmado)       | ❌ (não há feedback)              |  
| **Controle de Erros** | ✅ (retransmissão)                  | ❌ (perdeu, perdeu)               |  
| **Ordem dos Dados**   | ✅ (pacotes ordenados)              | ❌ (pode chegar fora de ordem)    |  
| **Velocidade**        | 🐢 (overhead de controle)           | 🚀 (rápido, sem burocracia)       |  

---

## **4. Por Que Isso Importa?**  
- **Com Conexão**: Ideal quando **precisão > velocidade** (ex.: bancos, downloads).  
- **Sem Conexão**: Ideal quando **velocidade > confiabilidade** (ex.: streaming, jogos).  

---

### **TL;DR**  
- **Com Conexão** = "Vamos combinar tudo antes de começar e confirmar cada passo."  
- **Sem Conexão** = "Jogo os dados e é isso, se chegar, chegar."  

