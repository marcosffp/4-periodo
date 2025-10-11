## 🧩 **Introdução à Camada de Rede**

A **Camada de Rede** atua entre a camada de enlace e a de transporte. Sua principal função é permitir a comunicação entre hosts em redes diferentes, garantindo que os pacotes cheguem ao destino corretamente.

### ✅ **Serviços da Camada de Rede**:
- **Empacotamento**: Formata os dados em pacotes.
- **Roteamento**: Decide o melhor caminho para o pacote.
- **Encaminhamento**: Envia o pacote pela interface correta.
- **Controle de erros**: Verifica integridade dos dados.
- **Controle de fluxo**: Regula a velocidade entre transmissor e receptor.
- **Controle de congestionamento**: Evita sobrecarga na rede.
- **Qualidade de Serviço (QoS)**: Garante desempenho conforme a aplicação.
- **Segurança**: Protege os dados durante a transmissão.

---

## 🔁 **Tipos de Redes e Comutação**

### 🔹 **Redes Não Orientadas à Conexão (Datagramas)**:
- Cada pacote é tratado de forma independente.
- Roteadores usam tabelas de roteamento baseadas no **endereço de destino**.
- Exemplo: IP (Internet Protocol).

### 🔹 **Redes com Circuitos Virtuais**:
- Estabelece um caminho pré-definido antes da transmissão.
- Usa **rótulos** para identificar o circuito.
- Oferece QoS e controle de congestionamento mais eficientes.

### 📊 **Comparação**:

| Característica          | Datagramas               | Circuitos Virtuais         |
|-------------------------|--------------------------|----------------------------|
| Endereçamento           | Endereço completo        | Rótulo curto               |
| Estado da conexão       | Não armazena estado      | Armazena estado por circuito |
| Roteamento              | Independente             | Todos os pacotes seguem a mesma rota |
| Controle de congestionamento | Difícil            | Fácil com alocação prévia |

---

## 🚦 **Controle de Congestionamento**

### 🔄 **Controle de Fluxo vs. Congestionamento**:
- **Controle de Fluxo**: Ponto a ponto (ex.: entre transmissor e receptor).
- **Controle de Congestionamento**: Global (envolve toda a rede).

### 🧠 **Tipos de Controle**:

#### 🔁 **Loop Aberto**:
- Age na prevenção, com regras fixas.
- Ex.: Projeto de rede com recursos superdimensionados.

#### 🔁 **Loop Fechado**:
- Usa **feedback** para detectar e corrigir congestionamento.
- Ex.: Ajuste dinâmico da taxa de transmissão.

### 🛠 **Estratégias de Controle**:
- **Contrapressão hop-by-hop**: Roteadores alertam vizinhos para reduzir tráfego.
- **Pacotes reguladores**: Alertam sobre congestionamento.
- **Escoamento de carga**: Descarta pacotes (randômico ou seletivo).
  - **Política do vinho**: Mantém pacotes antigos (ex.: transferência de arquivos).
  - **Política do leite**: Prefere pacotes novos (ex.: streaming).
- **Controle de admissão**: Impede a criação de novos circuitos em áreas congestionadas.

---

## 🌐 **Qualidade de Serviço (QoS)**

### 📌 **Parâmetros de QoS**:
- **Confiabilidade**: Entrega correta dos bits.
- **Retardo**: Tempo de entrega dos pacotes.
- **Flutuação (Jitter)**: Variação no tempo de chegada.
- **Largura de Banda**: Taxa de transmissão disponível.

### 🛠 **Técnicas para QoS**:
- **Superdimensionamento**: Aumento de capacidade (custo alto).
- **Buffers**: Suavizam o jitter, mas aumentam o atraso.
- **Modelagem de Tráfego**: Controla a taxa de envio na origem.
- **Algoritmo do Balde Furado (Leaky Bucket)**:
  - Transforma tráfego irregular em fluxo constante.
  - Descarta pacotes se o buffer estiver cheio.
- **Reserva de Recursos**:
  - Largura de banda, espaço em buffer e ciclos de CPU garantidos.

---

## 🖧 **Arquitetura dos Roteadores**

### 🧩 **Componentes Principais**:
- **Portas de entrada/saída**: Recebem e enviam pacotes.
- **Processador de roteamento**: Toma decisões de encaminhamento.
- **Malha de comutação**: Interconecta as portas.

### 🔀 **Tipos de Comutação**:
- **Crossbar**: Conexão direta entre entradas e saídas.
- **Banyan**: Comutação multietapa, mais escalável.

### 🏷 **Exemplo Real**:
- **Cisco CRS-1**: Roteador de alta capacidade usado em backbones.

---

## 📡 **Protocolos da Camada de Rede**

### 🔸 **IP (Internet Protocol)**:
- **IPv4**: Endereço de 32 bits, notação decimal pontuada.
- **IPv6**: Endereço de 128 bits, notação hexadecimal.
- **Classes de Endereços**:
  - A (0–127), B (128–191), C (192–223), D (multicast), E (reservado).
- **IPs Privados**:
  - 10.0.0.0/8, 172.16.0.0/12, 192.168.0.0/16.

### 🔸 **DHCP (Dynamic Host Configuration Protocol)**:
- Atribui IP automaticamente.
- Troca de mensagens: DISCOVER, OFFER, REQUEST, ACK.

### 🔸 **NAT (Network Address Translation)**:
- Traduz IPs privados para públicos.
- Tabela de mapeamento: IP privado ↔ IP público.

### 🔸 **ICMP (Internet Control Message Protocol)**:
- Mensagens de controle e diagnóstico.
- Exemplos:
  - **Ping**: Testa conectividade (mensagens Echo Request/Reply).
  - **Traceroute**: Mostra rota e RTT até o destino.

### 🔸 **ARP e RARP**:
- **ARP**: Descobre o endereço MAC a partir do IP.
- **RARP**: Descobre o IP a partir do MAC (usado em boot via rede).

---

## 🧭 **Algoritmos de Roteamento**

### 🧩 **Caminho Mais Curto (Dijkstra)**:
- Calcula a rota com menor custo.
- Usado em redes com topologia conhecida.

### 🌊 **Flooding (Inundação)**:
- Envia pacotes por todas as interfaces.
- Usa contador de saltos (TTL) para evitar loops.
- Robusto, mas gera tráfego excessivo.

### 📏 **Vetor de Distância (RIP)**:
- Roteadores trocam tabelas com vizinhos.
- **Problema**: Contagem até o infinito em caso de falha.

### 🔗 **Estado de Enlace (OSPF, IS-IS)**:
- Roteadores conhecem a topologia completa.
- Usam algoritmo de Dijkstra.
- Mais rápido e confiável que vetor de distância.

### 🗺 **Roteamento Hierárquico**:
- Divide a rede em regiões para reduzir o tamanho das tabelas.

---

## 📢 **Tipos de Comunicação**

### 👤 **Unicast**:
- Um para um.
- Ex.: Navegação web, email.

### 👥 **Multicast**:
- Um para muitos (grupo específico).
- Ex.: Videoconferência, streaming.

### 📣 **Broadcast**:
- Um para todos na rede.
- Ex.: ARP, DHCP.

---

## 🔄 **Transição do IPv4 para o IPv6**

### 🧩 **Estratégias de Migração**:
- **Pilha Dupla**: Roteadores suportam IPv4 e IPv6 simultaneamente.
- **Tunelamento**: Pacotes IPv6 encapsulados em IPv4.
- **Tradução de Cabeçalho**: Converte IPv6 para IPv4 e vice-versa.

---

## ✅ **Resumo Geral para Provas e Prática**

A **Camada de Rede** é responsável pelo **encaminhamento e roteamento** de pacotes entre redes. Utiliza **IP** como protocolo principal, com suporte a **QoS** e **controle de congestionamento**. Roteadores usam algoritmos como **Dijkstra**, **RIP** e **OSPF**. Protocolos como **ARP**, **DHCP**, **NAT** e **ICMP** são essenciais para o funcionamento da Internet. A migração para o **IPv6** é feita via **pilha dupla**, **tunelamento** ou **tradução**.

---
