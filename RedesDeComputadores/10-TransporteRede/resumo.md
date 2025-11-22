## 📘 PARTE 1 - CONTEÚDO DOS QUADROS

### 1️⃣ IP - INTERNET PROTOCOL

#### 🔹 O que é IP e "Sem Conexão/Sem Confirmação"

**IP (Internet Protocol)** é como o **sistema de endereçamento postal da internet**. Cada dispositivo conectado à rede tem um endereço IP único.

**"Sem conexão"** significa que não há "aperto de mãos" antes de enviar dados, como uma **carta comum**:
- Você coloca no correio sem saber se vai chegar
- Não há confirmação de recebimento
- Cada pacote segue caminhos independentes

**"Sem confirmação"** significa que o remetente não sabe se o pacote chegou.

**Analogia**: Enviar cartas pelo correio tradicional vs ligação telefônica.

#### 🔹 Classes de IP e Máscaras de Rede

```
CLASSE A: 0xxx xxxx.xxxx xxxx.xxxx xxxx.xxxx xxxx
           ↑    ↑←--------- 24 bits ---------→↑
          /8   Rede (7 bits)       Host (24 bits)
         127 redes ~16 milhões hosts cada

CLASSE B: 10xx xxxx.xxxx xxxx.xxxx xxxx.xxxx xxxx  
           ↑   ↑←---- 16 bits ---→↑←--- 16 bits ---→↑
          /16  Rede (14 bits)        Host (16 bits)
         16.384 redes ~65 mil hosts cada

CLASSE C: 110x xxxx.xxxx xxxx.xxxx xxxx.xxxx xxxx
           ↑  ↑←--- 24 bits ---→↑←- 8 bits -→↑
          /24 Rede (21 bits)       Host (8 bits)
         2 milhões redes 254 hosts cada
```

**Cálculo de endereços**:
- Classe A: 2⁷ = 128 redes × 2²⁴ = 16.777.216 hosts
- Classe B: 2¹⁴ = 16.384 redes × 2¹⁶ = 65.536 hosts  
- Classe C: 2²¹ = 2.097.152 redes × 2⁸ = 256 hosts

**Classes D e E**:
- **Classe D**: Multicast (224.0.0.0 a 239.255.255.255)
- **Classe E**: Experimental (240.0.0.0 a 255.255.255.255)

#### 🔹 Protocolos Auxiliares do IP

**DHCP (Dynamic Host Configuration Protocol)**:
```ascii
Cliente          Servidor DHCP
  | -------- DISCOVER -------> |
  | <------- OFFER ----------- |
  | -------- REQUEST --------> |
  | <------- ACK ------------- |
```
- **Função**: Atribui IP automaticamente
- **Como**: "Aluguel" de endereço por tempo determinado

**NAT (Network Address Translation)**:
```ascii
Rede Interna       Roteador        Internet
192.168.1.10 ---→  NAT ---→ 200.100.50.25:5000
192.168.1.11 ---→  NAT ---→ 200.100.50.25:5001
```
- **Problema que resolve**: Escassez de IPv4
- **Como**: Múltiplos IPs internos usam um IP externo

**ARP (Address Resolution Protocol)**:
- **Função**: Descobre qual MAC corresponde a um IP
- **Como**: Broadcast "Quem tem IP X.X.X.X?"

**ICMP (Internet Control Message Protocol)**:
- **Função**: Mensagens de erro e controle
- **Exemplo**: `ping` usa ICMP Echo Request/Reply

#### 🔹 TTL (Time To Live)

**O que é**: Contador que diminui a cada roteador
**Função**: Evitar loops infinitos
**Exemplo**: TTL=64 → pacote morre após 64 saltos

#### 🔹 Checksum no Cabeçalho IP

**Função**: Detectar erros no cabeçalho
**Como**: Soma de verificação dos campos
**Importante**: Só verifica cabeçalho, não dados

#### 🔹 Controle de Congestionamento

**"Pacote regulador hop-by-hop"**:
- Cada roteador pode sinalizar congestionamento
- **Descarte aleatório**: Remove pacotes randomicamente
- **Descarte político**: Prefere descartar tráfego menos importante

**Multimídia vs Download**:
- **Multimídia**: Prefere baixa latência (perda aceitável)
- **Download**: Prefere confiabilidade (sem perdas)

#### 🔹 Protocolos de Roteamento

**RIP (Routing Information Protocol)**:
- **Para**: Redes pequenas
- **Métrica**: Número de saltos (máximo 15)
- **Como**: Anuncia rotas a vizinhos

**OSPF (Open Shortest Path First)**:
- **Para**: Redes médias/grandes
- **Métrica**: Custo (largura de banda, delay)
- **Como**: Mapas completos da rede

**BGP (Border Gateway Protocol)**:
- **Para**: Internet
- **Métrica**: Políticas (econômicas, acordos)
- **Como**: Anúncios entre sistemas autônomos

---

### 2️⃣ TCP - TRANSMISSION CONTROL PROTOCOL

#### 🔹 TCP é Confiável e Orientado à Conexão

**Diferente do IP**, o TCP garante:
- Entrega na ordem correta
- Sem duplicatas
- Sem perdas

**Analogia**: **Telefonema** vs Carta
- Estabelece conexão → Conversa → Encerra conexão

#### 🔹 Three-Way Handshake

```ascii
Cliente            Servidor
  | ----- SYN -----> |
  | <--- SYN+ACK --- |
  | ----- ACK -----> |
```
**Passo a passo**:
1. **SYN**: "Posso conectar? Número sequência = X"
2. **SYN+ACK**: "Pode! Meu número sequência = Y, confirmo X+1"
3. **ACK**: "Confirmo Y+1, vamos conversar!"

#### 🔹 Cabeçalho TCP

```
 0                   1                   2                   3
 0 1 2 3 4 5 6 7 8 9 0 1 2 3 4 5 6 7 8 9 0 1 2 3 4 5 6 7 8 9 0 1
+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
|          Porta Origem         |        Porta Destino          |
+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
|                       Número de Sequência                     |
+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
|                   Número de Confirmação                       |
+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
| Offset| Reserv |C|E|U|A|P|R|S|F|          Janela              |
+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
|            Checksum           |       Ponteiro Urgente        |
+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
```

**Campos importantes**:
- **Portas**: Identificam aplicações (ex: 80=HTTP, 443=HTTPS)
- **Número sequência**: Ordem dos dados
- **Número confirmação**: Próximo byte esperado
- **Flags**: Controle da conexão
- **Janela**: Quantos bytes podem ser enviados

#### 🔹 Flags TCP

```
C E U A P R S F  →  Significado
0 0 0 1 0 0 0 0  →  ACK (Confirmação)
0 0 0 0 0 0 1 0  →  SYN (Sincronizar)
0 0 0 0 0 0 0 1  →  FIN (Finalizar)
1 0 0 0 0 0 0 0  →  CWR (Congestion Window Reduced)
0 1 0 0 0 0 0 0  →  ECE (ECN-Echo)
0 0 1 0 0 0 0 0  →  URG (Urgente)
0 0 0 0 1 0 0 0  →  PSH (Push - enviar agora)
0 0 0 0 0 1 0 0  →  RST (Reset - erro)
```

#### 🔹 Encerramento da Conexão

**Four-Way Close**:
```ascii
Cliente            Servidor
  | ----- FIN -----> |  (1) Cliente: "Acabei de enviar"
  | <---- ACK ------ |  (2) Servidor: "Entendi"
  | <---- FIN ------ |  (3) Servidor: "Eu também acabei"
  | ----- ACK -----> |  (4) Cliente: "OK, conexão fechada"
```

**Semifechamento**: Uma parte para de enviar mas continua recebendo
**Simultâneo**: Ambos enviam FIN ao mesmo tempo

#### 🔹 Regras de Confirmação (R1-R6)

**R1**: Confirma recebimento com ACK
**R2**: Timeout → retransmite
**R3**: ACK duplicado → possível perda
**R4**: Ordena pacotes fora de ordem
**R5**: Descarta duplicatas
**R6**: Controle de fluxo com janela

#### 🔹 Controle de Fluxo vs Congestionamento

**Controle de Fluxo**:
- **Quem**: Receptor
- **Problema**: Evitar sobrecarregar destinatário
- **Como**: Janela deslizante

**Controle de Congestionamento**:
- **Quem**: Transmissor  
- **Problema**: Evitar sobrecarregar rede
- **Como**: Slow Start, Congestion Avoidance

#### 🔹 Timeout e Retransmissão

**3 ACKs duplicados**: Indica perda de pacote → retransmite imediatamente
**Timeout**: Tempo muito longo sem resposta → retransmite

**Exemplo**:
```
Enviado: 1 2 3 4 5
Recebido: 1 2 4 5  → ACK=3 (duplicado)
Enviado: 3 (retransmissão)
```

---

## 📗 PARTE 2 - CONTEÚDO TEÓRICO COMPLEMENTAR

### 3️⃣ PROTOCOLOS DE TRANSMISSÃO DE DADOS

#### 🔹 Simplex
**Definição**: Transmissão em apenas uma direção
**Exemplo**: Rádio, TV aberta
**Problema**: Sem confirmação de recebimento

#### 🔹 Stop-and-Wait
```ascii
Envia P1 ---> 
          <--- ACK1
Envia P2 --->
          <--- ACK2
```
**Vantagem**: Simples
**Desvantagem**: Baixo aproveitamento (espera ACK)
**Uso**: Redes com alta confiabilidade

#### 🔹 Go-Back-N
```ascii
Janela = 3 pacotes
Envia: 1 2 3 4 5 6
Erro no 2 → Descarta 2 3 4 5 6
Reenvia a partir do 2: 2 3 4 5 6
```
**Vantagem**: Mais eficiente que Stop-and-Wait
**Desvantagem**: Retransmite pacotes bons
**Uso**: Redes com baixa taxa de erro

#### 🔹 Selective Repeat
```ascii
Envia: 1 2 3 4 5 6
Erro no 2 → Armazena 3 4 5 6
Reenvia apenas: 2
```
**Vantagem**: Máxima eficiência
**Desvantagem**: Complexidade no receptor
**Uso**: Redes com alta taxa de erro

**Analogia**: 
- **Stop-and-Wait**: Conversa por walkie-talkie
- **Go-Back-N**: Professor ditando matéria
- **Selective Repeat**: Colega emprestando caderno

### 4️⃣ SOCKETS

#### 🔹 O que é um Socket?
**Definição**: Ponto final de comunicação entre aplicações
**Função**: Interface entre aplicação e rede

```ascii
Aplicação ----- Socket ----- Rede
          ↑               ↑
      Interface       Protocolo
```

#### 🔹 Datagram Socket (UDP) vs Stream Socket (TCP)

**Datagram Socket (UDP)**:
```python
# Servidor
socket = socket(AF_INET, SOCK_DGRAM)
socket.bind(("0.0.0.0", 5000))
data, addr = socket.recvfrom(1024)
socket.sendto(response, addr)

# Cliente  
socket = socket(AF_INET, SOCK_DGRAM)
socket.sendto(data, ("servidor.com", 5000))
response, addr = socket.recvfrom(1024)
```

**Stream Socket (TCP)**:
```python
# Servidor
socket = socket(AF_INET, SOCK_STREAM)
socket.bind(("0.0.0.0", 5000))
socket.listen()
conn, addr = socket.accept()
data = conn.recv(1024)
conn.send(response)

# Cliente
socket = socket(AF_INET, SOCK_STREAM)
socket.connect(("servidor.com", 5000))
socket.send(data)
response = socket.recv(1024)
```

**Casos de uso**:
- **UDP**: DNS, VoIP, Jogos online, Streaming
- **TCP**: HTTP, FTP, Email, Transferência de arquivos

### 5️⃣ PORTAS TCP/UDP

#### 🔹 Intervalos de Portas

**0-1023**: Well-known (requer privilégios)
- 20/21: FTP
- 22: SSH
- 25: SMTP
- 53: DNS
- 80: HTTP
- 443: HTTPS

**1024-49151**: Registered (aplicações registradas)
- 3306: MySQL
- 5432: PostgreSQL
- 8080: HTTP alternativo

**49152-65535**: Dynamic (clientes efêmeros)

#### 🔹 Comandos para Verificar Portas

```bash
# Linux/Mac
netstat -tuln
ss -tuln
lsof -i :80

# Windows
netstat -an
```

**Riscos de Segurança**:
- Portas abertas desnecessárias = vetores de ataque
- Serviços com versões antigas vulneráveis
- Falta de firewall

### 6️⃣ UDP (USER DATAGRAM PROTOCOL)

#### 🔹 Cabeçalho UDP
```
 0      7 8     15 16    23 24    31
+--------+--------+--------+--------+
|    Porta Origem | Porta Destino   |
+--------+--------+--------+--------+
| Comprimento     |   Checksum      |
+--------+--------+--------+--------+
|              Dados                |
+-----------------------------------+
```

**Propriedades**:
- **Sem conexão**: Não estabelece sessão
- **Sem confirmação**: Não garante entrega
- **Não ordenado**: Pacotes podem chegar em ordem diferente

**Vantagens**:
- Baixa latência
- Overhead mínimo
- Controle na aplicação

**Usos típicos**:
- DNS queries
- Voz sobre IP (VoIP)
- Streaming de vídeo
- Jogos multiplayer

**Exemplo UDP**:
```ascii
Cliente            Servidor DNS
  | -- Query: google.com? --> |
  | <-- Response: 8.8.8.8 --- |
```

### 7️⃣ TCP - CABEÇALHO E FLAGS DETALHADOS

#### 🔹 Campos do Cabeçalho TCP

**Porta Origem/Destino** (16 bits cada): Identificam aplicações
**Número de Sequência** (32 bits): Posição do primeiro byte
**Número de Confirmação** (32 bits): Próximo byte esperado
**HLEN** (4 bits): Tamanho do cabeçalho em palavras de 32 bits
**Flags** (6 bits): Controle da conexão
**Janela** (16 bits): Tamanho da janela de recepção
**Checksum** (16 bits): Verificação de integridade
**Ponteiro Urgente** (16 bits): Posição de dados urgentes

#### 🔹 Significado das Flags

**SYN** (Synchronize): Inicia conexão
**ACK** (Acknowledge): Confirma recebimento  
**FIN** (Finish): Finaliza conexão
**RST** (Reset): Aborta conexão abruptamente
**PSH** (Push): Entrega dados imediatamente
**URG** (Urgent): Dados urgentes (usado com ponteiro)

**Exercício 1**: Qual flag indica que dados devem ser entregues imediatamente?
**Resposta**: PSH (Push)

### 8️⃣ ESTABELECIMENTO E ENCERRAMENTO

#### 🔹 Three-Way Handshake Detalhado

```ascii
Cliente (seq=x)        Servidor (seq=y)
  | --- SYN seq=x ----> |
  | <-- SYN seq=y, ACK x+1 -- |
  | --- ACK y+1 -----> |
```

**Estado do Cliente**: CLOSED → SYN_SENT → ESTABLISHED
**Estado do Servidor**: LISTEN → SYN_RCVD → ESTABLISHED

#### 🔹 Four-Way Close

```ascii
Cliente               Servidor
  | --- FIN seq=x ---> |  (Cliente: FIN_WAIT_1)
  | <-- ACK x+1 ------ |  (Cliente: FIN_WAIT_2)
  | <--- FIN seq=y --- |  (Cliente: TIME_WAIT)
  | --- ACK y+1 -----> |  (Cliente: CLOSED)
```

**TIME_WAIT**: Espera 2MSL (Maximum Segment Lifetime) para garantir que ACK final chegou

**Problemas**:
- **SYN Flood**: Ataque enviando muitos SYN sem completar handshake
- **Solução**: SYN cookies

### 9️⃣ REGRAS DE CONFIRMAÇÃO (R1-R6)

**R1**: Envia ACK ao receber dados válidos
**R2**: Timeout → retransmite segmento não confirmado
**R3**: 3 ACKs duplicados → retransmite imediatamente (Fast Retransmit)
**R4**: Reordena segmentos fora de ordem
**R5**: Descarta segmentos duplicados
**R6**: Implementa controle de fluxo com janela deslizante

**Exemplo R3**:
```
Enviado: 1 2 3 4 5
Recebido: 1 3 4 5 → ACK=2 (3 vezes)
Ação: Retransmite 2 imediatamente
```

### 🔟 CONTROLE DE FLUXO E CONGESTIONAMENTO

#### 🔹 Controle de Fluxo (Flow Control)

**Problema**: Evitar que receptor fique sobrecarregado
**Solução**: Janela deslizante (Sliding Window)

```ascii
Janela = 4 pacotes
[1][2][3][4][5][6][7][8]  → Buffer
↑        ↑
Enviados  Máximo
```

**Como funciona**: Receptor anuncia tamanho da janela no cabeçalho TCP

#### 🔹 Controle de Congestionamento

**Problema**: Evitar congestionar a rede
**Algoritmos**:

**Slow Start**:
- Janela começa pequena (1 MSS)
- Dobra a cada RTT (exponencial)
- Até encontrar congestionamento

**Congestion Avoidance**:
- Crescimento linear (+1 MSS por RTT)
- Após threshold

**Fast Retransmit/Fast Recovery**:
- Detecta perdas por ACKs duplicados
- Evita timeout desnecessário

**Analogia**: Estrada com tráfego
- **Slow Start**: Acelerar gradualmente ao entrar na estrada
- **Congestion Avoidance**: Manter distância segura
- **Fast Retransmit**: Desvio quando há acidente

### 1️⃣1️⃣ TCP - PROPRIEDADES

**Confiável**: Garante entrega, ordem e ausência de duplicatas
**Full-duplex**: Transmissão bidirecional simultânea
**Orientado à conexão**: Handshake antes de transmitir

**Aplicações que usam TCP**:
- HTTP/HTTPS (web)
- FTP (transferência arquivos)
- SMTP/POP/IMAP (email)
- SSH (acesso remoto)

**Por que aplicações em tempo real preferem UDP**:
- Latência mais previsível
- Sem retransmissões que atrasam
- Controle na aplicação

### 1️⃣2️⃣ FLAGS TCP - TABELA COMPLETA

| Flag | Nome | Significado | Uso |
|------|------|-------------|-----|
| SYN | Synchronize | Iniciar conexão | Handshake |
| ACK | Acknowledge | Confirmar recebimento | Respostas |
| FIN | Finish | Finalizar conexão | Encerramento |
| RST | Reset | Abortar conexão | Erros |
| PSH | Push | Entregar dados agora | Dados urgentes |
| URG | Urgent | Dados prioritários | Com ponteiro urgente |

**Combinações comuns**:
- **SYN=1, ACK=0**: Solicitação de conexão
- **SYN=1, ACK=1**: Resposta à solicitação
- **ACK=1**: Confirmação normal
- **FIN=1, ACK=1**: Encerramento gracioso

### 1️⃣3️⃣ MULTIMÍDIA SOBRE UDP

**Por que UDP para multimídia**:
- **Latência > Confiabilidade**: Retransmissão atrasa mais que a perda
- **Aplicação controla**: Decisões específicas do codec
- **Overhead menor**: Cabeçalho menor = mais dados por pacote

**Técnicas para melhorar qualidade**:

**FEC (Forward Error Correction)**:
- Adiciona dados redundantes
- Permite correção sem retransmissão

**Jitter Buffer**:
- Armazena pacotes antes de reproduzir
- Compensa variação de delay

**Protocolos**:
- **RTP (Real-time Transport Protocol)**: Transporte de mídia
- **RTCP (RTP Control Protocol)**: Controle e qualidade
- **SIP (Session Initiation Protocol)**: Sinalização de chamadas

### 1️⃣4️⃣ CLASSES E MÁSCARAS DE REDE

#### 🔹 Sistema de Classes (Obsoleto, mas importante entender)

**Classe A**: /8 (255.0.0.0) - 16M hosts
**Classe B**: /16 (255.255.0.0) - 65K hosts  
**Classe C**: /24 (255.255.255.0) - 254 hosts

**Problema**: Escassez de endereços
**Solução**: CIDR (Classless Inter-Domain Routing)

#### 🔹 CIDR - Notação /X

**/8**: 255.0.0.0 → 16.777.214 hosts
**/16**: 255.255.0.0 → 65.534 hosts
**/24**: 255.255.255.0 → 254 hosts
**/28**: 255.255.255.240 → 14 hosts

**Cálculo de hosts**: 2^(32-X) - 2
- -2 para rede e broadcast

**Exercício**: Rede 192.168.1.0/28
- Máscara: 255.255.255.240
- Hosts: 2^(32-28) - 2 = 14
- Endereços: 192.168.1.1 a 192.168.1.14

### 1️⃣5️⃣ PROTOCOLOS AUXILIARES

#### 🔹 DHCP (Dynamic Host Configuration Protocol)

**Função**: Atribuição automática de IP
**Processo DORA**:
- **Discover**: Cliente busca servidor
- **Offer**: Servidor oferece IP
- **Request**: Cliente aceita oferta  
- **Ack**: Servidor confirma

**Problemas**: Servidor indisponível, conflitos de IP

#### 🔹 NAT (Network Address Translation)

**Função**: Traduz IPs privados para público
**Tipos**:
- **NAT Estático**: Mapeamento fixo
- **NAT Dinâmico**: Pool de IPs públicos
- **PAT (NAT Overload)**: Múltiplos para um (portas)

**Problemas**: Quebra alguns protocolos, complexidade

#### 🔹 ARP (Address Resolution Protocol)

**Função**: Mapeia IP → MAC
**Processo**:
1. Broadcast: "Quem tem IP X?"
2. Resposta: "Eu tenho, MAC Y"

**Problemas**: ARP spoofing, cache poisoning

#### 🔹 ICMP (Internet Control Message Protocol)

**Função**: Mensagens de controle e erro
**Usos**:
- **ping**: Echo Request/Reply
- **traceroute**: TTL expirado
- **Destino inacessível**: Relata erros

### 1️⃣6️⃣ ROTEAMENTO (RIP, OSPF, BGP)

#### 🔹 RIP (Routing Information Protocol)

**Tipo**: Distance Vector
**Métrica**: Saltos (máximo 15)
**Atualizações**: A cada 30 segundos
**Vantagem**: Simples
**Desvantagem**: Lento para convergência, limite de saltos

#### 🔹 OSPF (Open Shortest Path First)

**Tipo**: Link State
**Métrica**: Custo (baseado em banda)
**Atualizações**: Quando há mudanças
**Vantagem**: Rápida convergência, sem limite de saltos
**Desvantagem**: Complexo, consome mais recursos

#### 🔹 BGP (Border Gateway Protocol)

**Tipo**: Path Vector
**Métrica**: Políticas (não técnica)
**Escopo**: Internet (entre AS)
**Vantagem**: Extremamente escalável
**Desvantagem**: Complexidade de configuração

**Diferença**:
- **RIP/OSPF**: Intra-domínio (dentro de uma organização)
- **BGP**: Inter-domínio (entre organizações)

### 1️⃣7️⃣ CONTROLE DE CONGESTIONAMENTO

#### 🔹 Algoritmos TCP

**Tahoe**:
- Slow Start → Congestion Avoidance
- Ao detectar perda: Janela = 1 MSS

**Reno**:
- Fast Retransmit/Recovery
- Janela = Janela/2 (não volta para 1)

#### 🔹 RED (Random Early Detection)

**Função**: Prevenir congestionamento
**Como**: Descarta pacotes aleatoriamente antes do buffer encher
**Vantagem**: Evita sincronização global

**Analogia de Engarrafamento**:
- **Congestionamento**: Trânsito parado
- **RED**: Controladores de tráfego impedindo entrada
- **Slow Start**: Acelerar gradualmente ao entrar na via

### 1️⃣8️⃣ CHECKSUM (UDP/TCP)

#### 🔹 Cálculo do Checksum

**Função**: Detectar erros no cabeçalho e dados
**Como**: Soma de complemento de 1 dos segmentos

**Processo**:
1. Divide dados em palavras de 16 bits
2. Soma todas as palavras
3. Inverte os bits (complemento de 1)
4. Resultado = checksum

**UDP vs TCP**:
- **UDP**: Opcional (pode ser 0)
- **TCP**: Obrigatório

**Limitações**: Não detecta todos os erros, especialmente rearranjos

### 1️⃣9️⃣ EXEMPLOS PRÁTICOS DE COMANDOS

#### 🔹 ping
```bash
$ ping google.com
PING google.com (142.250.218.14): 56 data bytes
64 bytes from 142.250.218.14: icmp_seq=0 ttl=116 time=15.234 ms
64 bytes from 142.250.218.14: icmp_seq=1 ttl=116 time=14.987 ms
```
**O que mostra**: Latência, TTL, perda de pacotes

#### 🔹 traceroute/tracert
```bash
$ traceroute google.com
1  192.168.1.1 (192.168.1.1)  1.234 ms
2  10.0.0.1 (10.0.0.1)  5.678 ms
3  200.100.50.25 (200.100.50.25)  10.123 ms
```
**O que mostra**: Caminho até destino, latência por hop

#### 🔹 netstat/ss
```bash
$ netstat -tuln
Proto Recv-Q Send-Q Local Address Foreign Address State
tcp   0      0     0.0.0.0:22    0.0.0.0:*       LISTEN
tcp   0      0     127.0.0.1:5432 0.0.0.0:*       LISTEN
```
**O que mostra**: Portas abertas, conexões ativas

### 2️⃣0️⃣ RESUMO FINAL - MAPA MENTAL

```
REDES DE COMPUTADORES
│
├── IP (Internet Protocol)
│   ├── Endereçamento (IPv4/IPv6)
│   ├── Roteamento (RIP, OSPF, BGP)
│   ├── Protocolos Auxiliares (DHCP, NAT, ARP, ICMP)
│   └── Controle Congestionamento
│
├── TRANSPORTE
│   ├── TCP (Confiável, Conexão)
│   │   ├── Handshake (SYN, SYN-ACK, ACK)
│   │   ├── Controle Fluxo (Janela Deslizante)
│   │   ├── Controle Congestionamento (Slow Start, AIMD)
│   │   └── Encerramento (FIN, ACK)
│   │
│   └── UDP (Não Confiável, Sem Conexão)
│       ├── Baixa Latência
│       ├── Overhead Mínimo
│       └── Usos: DNS, VoIP, Streaming
│
├── APLICAÇÃO
│   ├── Sockets (TCP Stream, UDP Datagram)
│   ├── Portas (0-65535)
│   │   ├── Well-known (0-1023)
│   │   ├── Registered (1024-49151)
│   │   └── Dynamic (49152-65535)
│   └── Exemplos: HTTP(80), HTTPS(443), SSH(22), DNS(53)
│
└── CONCEITOS CHAVE
    ├── Confiabilidade vs Latência
    ├── Conexão vs Sem Conexão
    ├── Controle Fluxo vs Congestionamento
    └── End-to-end vs Hop-by-hop
```

---