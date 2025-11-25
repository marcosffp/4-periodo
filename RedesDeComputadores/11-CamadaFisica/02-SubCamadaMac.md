# Resumo Compacto - Subcamada MAC

## O Básico

A **Subcamada MAC** resolve um problema simples: quando vários dispositivos compartilham o mesmo canal de comunicação (como WiFi ou Ethernet antiga), quem fala primeiro? Sem regras, todo mundo transmite junto e vira bagunça - é aí que a MAC entra, organizando quem usa o canal e quando.

**Importante:** A MAC não garante entrega - ela só organiza o acesso. Se os dados se perderem depois, problema de outra camada.

---

## Alocação: Estática vs Dinâmica

**Alocação Estática** reserva um pedaço do canal para cada usuário o tempo todo. Problema: desperdício absurdo, já que ninguém transmite direto - todo mundo fica em silêncio 99,9% do tempo.

**Alocação Dinâmica** usa um canal compartilhado. Quer transmitir? Tente usar! Se outra pessoa tentar ao mesmo tempo, acontece uma **colisão** (os dados viram lixo e precisam ser reenviados).

---

## Protocolos: A Evolução do Caos à Ordem

### ALOHA Puro (1970)
O mais primitivo: transmita quando quiser. Se colidir, espere um tempo aleatório e tente de novo. Aproveitamento miserável: **18%** do canal.

### Slotted ALOHA
Melhoria: divide o tempo em intervalos (slots). Só pode transmitir no início de cada slot. Dobra o desempenho para **37%**, mas ainda é pouco.

### CSMA (Carrier Sense Multiple Access)
A grande sacada: **ouça antes de falar**. Se alguém está transmitindo, espere!

Três variações:

**1-Persistente (o ansioso):** Fica ouvindo. Canal livre? Transmite na hora. Problema: se dois estão esperando, transmitem juntos → colisão.

**Não-Persistente (o educado):** Canal ocupado? Espera um tempo aleatório e verifica de novo. Menos colisões, mas desperdiça tempo.

**p-Persistente (o estratégico):** Canal livre? Transmite com probabilidade *p* ou espera mais um slot com probabilidade *1-p*. Equilibra velocidade e segurança.

### CSMA/CD (a estrela da Ethernet)
**CD = Collision Detection**. A inovação: além de ouvir antes, você ouve **enquanto** fala. Detectou colisão? Para imediatamente e envia um sinal avisando todo mundo.

**Backoff Exponencial:** Após colisão, espera um tempo aleatório que cresce exponencialmente a cada nova colisão (evita sobrecarga quando a rede está lotada).

Estados: **Disponível** (em repouso) → **Transmissão** (enviando) → **Contenção** (esperando após colisão).

---

## Protocolos Sem Colisão

**Mapa de Bits:** Cada estação "levanta a mão" antes de transmitir. Depois, falam em ordem. Zero colisões, mas tem overhead.

**Token Ring:** Uma "ficha virtual" circula. Só quem tem a ficha pode transmitir. Justo e sem colisões, mas se o token se perde, a rede trava.

---

## Ethernet (IEEE 802.3)

A tecnologia de rede local mais usada do mundo. Começou nos anos 70, evoluiu de 10 Mbps até 10 Gbps (e além). Venceu por ser barata, simples e escalável.

**Topologia:** De barramento (um cabo único compartilhado) nos anos 90 para **estrela** (todos conectados a um ponto central) hoje.

### Quadro Ethernet

```
[Preâmbulo] [MAC Destino] [MAC Origem] [Tipo] [Dados] [CRC]
```

- **Preâmbulo (8 bytes):** Sincroniza transmissor e receptor
- **Endereços MAC (6 bytes cada):** De quem e para quem
- **Tipo (2 bytes):** Qual protocolo está sendo usado (IP, etc.)
- **Dados (46 a 1500 bytes):** O conteúdo real (mínimo 46 para garantir detecção de colisão)
- **CRC (4 bytes):** Verifica erros. Se falhar, descarta em silêncio

**Tamanho mínimo:** 64 bytes (sem preâmbulo) - necessário para CSMA/CD funcionar em redes de até 2,5 km.

### Endereço MAC

48 bits (12 dígitos hexadecimais). Exemplo: `58:50:76:AA:BB:CC`

- **Primeiros 24 bits:** Fabricante
- **Últimos 24 bits:** Número único
- **Tipos:** Unicast (um destinatário), Multicast (grupo), Broadcast (FF:FF:FF:FF:FF:FF = todos)

### Codificação Manchester
Usada na Ethernet de 10 Mbps. Cada bit tem uma transição no meio: bit 1 vai de alto→baixo, bit 0 vai de baixo→alto. Permite sincronização sem relógio centralizado.

### Serviço Ethernet
**Sem conexão:** Não avisa antes de enviar.
**Não confiável:** Não confirma recebimento. Se perdeu, perdeu (TCP resolve depois se necessário).

---

## Evolução da Ethernet

**10BaseT:** 10 Mbps, par trançado, 100m, conector RJ-45
**Fast Ethernet (100BaseT):** 100 Mbps, aboliu coaxial
- **100Base-TX:** Par trançado CAT5, 2 pares, full-duplex
**Gigabit Ethernet:** 1 Gbps, mantém formato do quadro (compatibilidade)
**10 Gigabit Ethernet:** 10 Gbps, data centers

*Full-duplex* = transmite e recebe ao mesmo tempo (como telefone). *Half-duplex* = ou transmite ou recebe (como walkie-talkie).

---

## Hubs vs Switches

**Hub (obsoleto):**
- Repete tudo para todas as portas
- Burro (camada física)
- Um único domínio de colisão = caos
- Não entende MAC

**Switch (rei das LANs):**
- Inteligente (camada de enlace)
- Lê endereços MAC
- Encaminha apenas para o destinatário
- Cada porta = domínio de colisão separado
- Auto-aprendizado: constrói tabela de MACs sozinho
- Transparente: computadores nem sabem que existe

---

## WiFi (802.11) e CSMA/CA

**Por que não CSMA/CD no WiFi?**
Detectar colisão no ar é impossível - seu próprio sinal é forte demais para ouvir outros.

**Solução: CSMA/CA (Collision Avoidance)**
- Ouve o canal
- Se livre, espera um tempo (DIFS) e transmite
- Se ocupado, sorteia um tempo aleatório (janela de contenção) e espera
- **ACK obrigatório:** Receptor confirma recebimento (diferente da Ethernet cabeada)

**NAV (Network Allocation Vector):** "Reserva" o canal antes de transmissões grandes:
1. Envia **RTS** (posso transmitir?)
2. Recebe **CTS** (pode!)
3. Todos ajustam um timer interno e esperam

**Intervalos de prioridade:**
- **SIFS:** Menor tempo (ACKs = prioridade máxima)
- **DIFS:** Tempo normal (dados)
- **EIFS:** Tempo longo (após erro)

**Quadro WiFi:** Mais complexo que Ethernet - pode ter até 4 endereços MAC (origem, destino, AP, roteamento entre APs).

---

## Resumão Final

**Problema:** Múltiplos dispositivos, um canal.

**Evolução:** ALOHA (caos) → CSMA (ouça antes) → CSMA/CD (detecta colisão) → CSMA/CA (evita colisão).

**Ethernet cabeada:** CSMA/CD, switches inteligentes, endereços MAC únicos, sem confirmação.

**WiFi:** CSMA/CA, ACK obrigatório, impossível detectar colisão no ar.

**Dispositivos:** Hubs (burros, obsoletos) vs Switches (inteligentes, dominantes).

**Velocidades:** 10 Mbps → 100 Mbps → 1 Gbps → 10 Gbps → infinito e além.

Pronto! Agora você sabe como as redes evitam que todo mundo grite ao mesmo tempo. 🎯