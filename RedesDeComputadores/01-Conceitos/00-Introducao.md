## Comunicação de Dados e Redes de Computadores

### **1. Introdução e Bibliografia**
A disciplina de **Redes de Computadores** é ministrada pelo **Prof. Alexandre Teixeira** e utiliza como referência bibliográfica obras clássicas da área, como:
- Tanenbaum, Kurose, Peterson, Forouzan, Stallings.

---

### **2. Definição e Conceitos Básicos**
- **Rede de Computadores**: Conjunto de computadores autônomos interconectados por uma tecnologia comum.
- Elementos fundamentais:
  - Serviços de Rede
  - Meio de Transmissão
  - Protocolos de Comunicação

---

### **3. Aplicações das Redes**
#### **Aplicações Comerciais:**
- Compartilhamento de recursos
- Desktop remoto
- Comércio eletrônico
- Confiabilidade
- Economia
- Eficiência

#### **Aplicações Residenciais:**
- Conectividade
- Redes sociais
- Mensagens instantâneas
- IPTV
- Computação ubíqua
- RFID
- Redes de energia elétrica
- P2P (peer-to-peer)
- Entretenimento interativo

---

### **4. Modelos de Comunicação**
#### **Modelo Cliente-Servidor:**
- Comunicação hierárquica.
- Servidores com hardware especializado e serviços centralizados.
- Clientes fazem requisições via rede.

#### **Modelo Peer-to-Peer (P2P):**
- Não há distinção clara entre clientes e servidores.
- Comunicação não hierárquica.
- Cada nó pode atuar como cliente e servidor simultaneamente.

---

### **5. Elementos de um Sistema de Comunicação**
- **Fonte de Informação** → **Codificador de Fonte** → **Codificador de Canal** → **Transmissor** → **Canal** (com ruído) → **Receptor** → **Decodificador de Canal** → **Decodificador de Fonte** → **Destino**
- Unidades de medida: **sh/s** (símbolos por segundo), **bit/s**, **Baud**.

---

### **6. Hardware de Rede**
Classificação segundo:
- **Tecnologia de transmissão**
- **Escala geográfica**

#### **Tecnologia de Transmissão:**
- **Redes de Difusão (Broadcast/Multicast):**
  - Canal único compartilhado.
  - Mensagens recebidas por todas as máquinas.
  - **Broadcasting**: mensagem para todas as máquinas.
  - **Multicasting**: mensagem para um grupo específico.

- **Redes Ponto a Ponto (Point-to-Point):**
  - Comunicação direta entre pares.
  - Pacotes podem passar por múltiplos nós.
  - Uso de algoritmos de roteamento.

#### **Escala Geográfica:**
| Tipo de Rede       | Abrangência         | Exemplos                          |
|---------------------|---------------------|-----------------------------------|
| PAN (WPAN)          | Alguns metros       | Bluetooth (IEEE 802.15)           |
| LAN (WLAN)          | Até alguns km       | Ethernet, Wi-Fi (IEEE 802.11)     |
| MAN (WMAN)          | Centenas de km      | WiMAX (IEEE 802.16), Metro Ethernet |
| WAN                 | País/Continente     | Internet, MPLS, SDH               |

---

### **7. Topologias de Rede**
- **Barramento (Bus)**
- **Anel (Ring)**
- **Estrela (Star)**
- **Estrela Estendida**
- **Hierárquica**
- **Malha (Mesh)**

---

### **8. Modelos de Referência em Camadas**
#### **Modelo OSI (7 Camadas):**
1. **Física**: bits, sinais, interfaces físicas.
2. **Enlace**: quadros (frames), controle de erro, acesso ao meio.
3. **Rede**: roteamento, endereçamento lógico, QoS.
4. **Transporte**: comunicação fim-a-fim, confiabilidade, controle de fluxo.
5. **Sessão**: controle de diálogo, sincronização, tokens.
6. **Apresentação**: formatação, criptografia, conversão de dados.
7. **Aplicação**: serviços de rede (HTTP, FTP, SMTP, etc.).

#### **Modelo TCP/IP (4 Camadas):**
1. **Aplicação**: equivalentes às camadas 5, 6 e 7 do OSI.
2. **Transporte**: TCP (conexão, confiável) e UDP (não-conexão, não-confiável).
3. **Internet**: IP, roteamento.
4. **Host/Rede**: interface com a rede física.

#### **Comparação OSI vs. TCP/IP:**
- **OSI**: teórico, bem estruturado, pouco usado na prática.
- **TCP/IP**: prático, amplamente utilizado, mas menos formal.

---

### **9. Questões de Projeto das Camadas**
- **Endereçamento**: identificação de hosts e processos.
- **Tipo de Canal**:
  - Simplex: comunicação unidirecional.
  - Half-Duplex: bidirecional não simultâneo.
  - Full-Duplex: bidirecional simultâneo.
- **Controle de Erros**: detecção e correção.
- **Garantia de Entrega**: confiabilidade com acknowledgments.
- **Ordenação de Pacotes**: sequenciamento.
- **Controle de Fluxo**: evitar sobrecarga do receptor.
- **Tamanho da Mensagem**: fragmentação e remontagem.
- **Multiplexação**: compartilhamento de conexão.
- **Roteamento**: escolha do melhor caminho.

---

### **10. Classificação da Transmissão**
- **Orientada à Conexão**: estabelece canal dedicado (ex: TCP).
- **Não Orientada à Conexão**: cada pacote é independente (ex: UDP).
- **Confiável**: com confirmação de entrega.
- **Não Confiável**: sem confirmação, mais rápido.

---

### **11. Exemplos de Redes**
- **Ethernet**: padrão LAN com cabo compartilhado.
- **Internet**: baseada em ISP, POP, backbones, NAP, server farms.
- **Frame Relay**: WAN barata, com quadros grandes, sem controle de erro fim-a-fim.
- **ATM**: orientado a conexão, células fixas de 53 bytes, usada em backbones.
- **Metro Ethernet**: extensão da Ethernet em MAN.
- **MPLS**: roteamento baseado em rótulos para tráfego IP.
- **Telefonia Móvel (3G/4G/5G)**: redes celulares com comutação de pacotes e circuitos.
- **Wi-Fi (IEEE 802.11)**: redes locais sem fio.
- **RFID**: identificação por radiofrequência para rastreamento.

---

### **12. Equipamentos de Rede**
- **Hub**: regenera sinal (camada 1).
- **Switch**: comutação baseada em endereços MAC (camada 2).
- **Roteador**: roteamento baseado em endereços IP (camada 3).
- **Gateway**: converte protocolos entre redes heterogêneas.

---

### **13. Padrões e Organismos**
- **ISO**, **ANSI**, **IEEE**, **ABNT**, **IETF**, **ETSI**, **EIA**, **TIA**, **DIN**, **JSA**.

---

### **14. Encapsulamento e Endereçamento**
- **Encapsulamento**: cada camada adiciona cabeçalhos aos dados.
- **Nomes dos pacotes por camada**:
  - Aplicação: Mensagem
  - Transporte: Segmento (TCP) / Datagrama (UDP)
  - Rede: Datagrama (IP)
  - Enlace: Quadro (Frame)
  - Física: Bits

- **Endereçamento**:
  - Nomes (DNS)
  - Portas (Transporte)
  - Endereços lógicos (IP)
  - Endereços físicos (MAC)

---

### **15. Heterogeneidade de Redes**
- Integração de diferentes tecnologias: satélite, fibra óptica, Wi-Fi, WiMAX, celular, Ethernet, etc.

---

### **16. Topologias Corporativas e WAN**
- Uso de **sub-redes**, **VLANs**, **roteadores**, **switches**, **firewalls**.
- Modelagem em camadas para redes corporativas e WAN.

---
