# Resumo Completo - Camada Física e Fundamentos de Comunicação

## 1. O que é a Camada Física?

A Camada Física é como o "carteiro" das redes de computadores. Ela cuida de toda a parte física da transmissão de dados: ativar e desativar conexões, transformar seus dados em sinais que podem viajar por cabos ou pelo ar, e garantir que tudo chegue na ordem certa.

**Principais funções:**
- Ativar e desativar conexões físicas (como ligar/desligar um cabo)
- Juntar vários cabos para criar um caminho maior
- Transformar dados em sinais e vice-versa
- Controlar e sincronizar a transmissão (garantir que emissor e receptor estejam "no mesmo ritmo")
- Avisar quando algo não está funcionando bem

## 2. Como os Dados Viajam: Sinais Eletromagnéticos

**Conceito básico:** Computadores trabalham com 0s e 1s, mas esses números não podem simplesmente "voar" pelo ar ou cabo. Eles precisam ser transformados em **ondas eletromagnéticas** (como ondas de rádio, luz, sinais elétricos).

### Conceitos importantes sobre ondas:

**Frequência:** É quantas vezes a onda "sobe e desce" por segundo. Medida em Hertz (Hz).
- *Analogia:* Imagine balançar uma corda. Se você balançar 10 vezes por segundo, a frequência é 10 Hz.

**Amplitude:** É a "altura" da onda. Quanto maior a amplitude, mais forte o sinal.
- *Analogia:* É como o volume do som. Alto volume = grande amplitude.

**Comprimento de Onda (λ):** É a distância entre dois "picos" consecutivos da onda.
- *Relação importante:* Frequência alta = comprimento de onda curto (e vice-versa)

**Espectro Eletromagnético:** É o "catálogo" de todas as ondas possíveis, desde ondas de rádio (grandes e lentas) até raios gama (minúsculas e rápidas).

## 3. Tipos de Sinais

### Sinal Analógico
- Varia continuamente, sem "saltos"
- Como um termômetro de mercúrio que mostra qualquer temperatura
- Exemplo: sua voz, ondas de rádio FM

### Sinal Digital
- Tem apenas valores específicos (0 ou 1, ligado ou desligado)
- Como um interruptor de luz: ou está ligado ou desligado, sem meio-termo
- Exemplo: dados de computador

### Conversões possíveis:
- **Dados analógicos → Digital:** Sua voz no telefone é transformada em números
- **Dados digitais → Analógico:** Seu modem transforma dados do computador em sinais que viajam pela linha telefônica

## 4. Problemas na Transmissão

### Ruído
É qualquer interferência indesejada que "suja" o sinal.
- *Analogia:* Como estática no rádio ou chiado no telefone
- **Relação Sinal/Ruído:** Quanto maior, melhor (sinal forte, ruído fraco)

### Atenuação
O sinal vai "enfraquecendo" conforme viaja.
- *Analogia:* Como sua voz que fica mais fraca quanto mais longe você está
- Por isso cabos muito longos precisam de repetidores (amplificadores)

### Distorção
O sinal muda de forma durante a viagem.
- *Analogia:* Como uma mensagem no "telefone sem fio" que chega distorcida no final

## 5. Medindo o Desempenho

### Largura de Banda
É a "quantidade de estrada" disponível para os dados viajarem. Quanto maior, mais dados podem passar ao mesmo tempo.
- Medida em Hz (para frequências) ou bps (bits por segundo, para dados)
- *Analogia:* Uma estrada de 4 pistas transporta mais carros que uma de 1 pista

### Taxa de Transmissão
Quantos bits estão sendo enviados por segundo (bps, Kbps, Mbps, Gbps)

### Latência Total (tempo que um dado leva para ir de A até B)
**Fórmula:** Latência = Overhead de envio + Tempo de voo + (Tamanho do pacote / Largura de banda) + Overhead de recebimento

Onde:
- **Tempo de voo:** Tempo para o primeiro bit chegar
- **Tempo de transmissão:** Tempo para o pacote inteiro passar
- **Overhead de envio/recebimento:** Tempo de preparação antes de enviar e processamento ao receber

*Analogia completa:* É como enviar uma carta: tempo para escrever (overhead envio) + tempo no correio (voo) + tempo para entregar todas as páginas (transmissão) + tempo do destinatário ler (overhead recebimento)

## 6. Banda Base vs Banda Larga

### Banda Base (Baseband)
- Sinalização **digital**
- Transmite **apenas um sinal por vez**
- Alta velocidade (Mbps, Gbps), mas curtas distâncias
- Exemplo: Ethernet, USB

### Banda Larga (Broadband)
- Sinalização **analógica**
- Transmite **vários sinais ao mesmo tempo** (em frequências diferentes)
- Menor velocidade individual, mas funciona em longas distâncias
- Exemplo: Rádio, TV a cabo, ADSL

*Analogia:* Banda base é como uma rodovia onde passa apenas um tipo de veículo por vez, mas muito rápido. Banda larga é como várias ruas paralelas, cada uma com um tipo diferente de veículo.

## 7. Meios de Transmissão

### Cabo Par Trançado
**O que é:** Dois fios de cobre trançados um no outro, cobertos por plástico.

**Por que trançado?** O trançado elimina interferências elétricas.

**Tipos:**
- **UTP:** Sem blindagem (mais comum, mais barato)
- **STP:** Com blindagem (proteção extra contra interferência)
- **FTP:** Folheado (proteção intermediária)

**Categorias (do mais antigo ao mais moderno):**
- **CAT 3:** Até 10 Mbps, 16 MHz (antigas redes Ethernet)
- **CAT 5:** Até 100 Mbps, 100 MHz
- **CAT 5e:** Até 1 Gbps, 100 MHz (melhoria da CAT 5)
- **CAT 6:** Até 1 Gbps (100m) ou 10 Gbps (55m), 250 MHz
- **CAT 6a:** 10 Gbps em 100m, 500 MHz
- **CAT 7:** 10 Gbps em 100m, 600 MHz

**Limitação:** Normalmente até 100 metros sem repetidor
**Conector:** RJ-45 (aquele do cabo de internet comum)

### Fibra Óptica
**O que é:** Fio de vidro finíssimo que transmite luz em vez de eletricidade.

**Estrutura (de dentro para fora):**
1. Núcleo de vidro (onde a luz viaja)
2. Casca de vidro (mantém a luz refletindo dentro)
3. Camadas de proteção (plástico, kevlar, etc.)

**Tipos:**

1. **Multimodo de Índice Degrau**
   - Núcleo grosso (100-1000 μm)
   - Baixa capacidade, alta atenuação
   - Mais simples e barata

2. **Multimodo de Índice Gradual**
   - Núcleo médio (50, 62.5 ou 85 μm)
   - Melhor desempenho que a anterior
   - Atenuação até 3 dB/Km, banda até 1 GHz/Km

3. **Monomodo**
   - Núcleo muito fino (2-10 μm)
   - Altíssimo desempenho
   - Atenuação 0,2-0,5 dB/Km, banda 10-100 GHz
   - Pode ir até 50 km sem regeneração!

**Vantagens:**
- Largura de banda enorme
- Viaja distâncias muito longas
- Imune a interferências eletromagnéticas
- Leve e resistente
- Impossível fazer "escuta" no cabo

**Desvantagens:**
- Cara para instalar e manter
- Precisa mão de obra especializada
- Unidirecional (precisa de 2 fibras: uma para enviar, outra para receber)

### Cabo Coaxial
**O que é:** Cabo com fio central condutor, isolamento, blindagem metálica e capa externa.

**Era muito usado antigamente, hoje está praticamente obsoleto em redes locais.**

**Características:**
- Até 10 MHz de frequência
- Até 10 Mbps
- Máximo 185 metros sem repetidor
- Conectores BNC
- Exemplo: RG-58 (redes antigas), RG-59 (TV a cabo)

## 8. Rede de Telefonia (PSTN)

**Estrutura:**
1. **Loop Local:** O "último quilômetro" - cabo que vai da sua casa até a central telefônica (par trançado analógico)
2. **Troncos:** Conexões entre centrais (fibra óptica digital)
3. **Estações de Comutação:** "Operadoras automáticas" que conectam as chamadas

**Curiosidade:** Sua voz é analógica apenas no trecho de casa até a central. Depois, vira digital e viaja pela rede, voltando a ser analógica no destino.

### ADSL (Internet pela linha telefônica)

**Problema tradicional:** Telefone usava apenas 3.100 Hz de banda, limitando a velocidade a 56 kbps.

**Solução ADSL:** Remove esse filtro e usa toda a largura de banda do cabo.

**Características:**
- **Assimétrico:** Velocidade de download diferente do upload (ex: 8 Mbps down, 1 Mbps up)
- Funciona como 350 modems trabalhando em paralelo, cada um em frequência diferente
- Quanto mais longe da central, menor a velocidade

## 9. Internet a Cabo

Usa a mesma infraestrutura da TV a cabo. A frequência é dividida em canais: alguns para TV, outros para internet (downstream e upstream).

## 10. Redes Sem Fio (Wireless)

### Bandas de Frequência
- **ISM (Industrial, Scientific and Medical):** Bandas livres que não precisam de licença (2,4 GHz e 5 GHz)

### Padrões WiFi (802.11)

**802.11a:**
- 5 GHz
- Até 54 Mbps (real: ~20 Mbps)
- Alcance: 50m
- Gasta muita energia

**802.11b:**
- 2,4 GHz
- Até 11 Mbps
- Alcance: 30m a 11 Mbps, 90m a 1 Mbps
- Foi muito popular

**802.11g:**
- 2,4 GHz
- Até 54 Mbps
- Compatível com 802.11b
- Gasta menos energia que o "a"

**802.11n:**
- 2,4 GHz ou 5 GHz
- Até 600 Mbps
- Usa múltiplas antenas
- Compatível com padrões anteriores

**Melhorias adicionais:**
- **802.11e:** Qualidade de serviço
- **802.11i:** Segurança (WPA2)

### Arquitetura WiFi

**Modo Infraestrutura:**
- Usa um **Access Point (AP)** - o "roteador WiFi"
- Forma um **BSS (Basic Service Set)** - uma "célula" WiFi
- AP conecta dispositivos sem fio à rede cabeada

**Modo Ad Hoc:**
- Dispositivos conversam diretamente entre si
- Sem AP no meio

### Bluetooth (802.15)

**Características:**
- Rede pessoal de curto alcance (menos de 10m)
- 2,4 GHz
- Até 721 kbps
- Substitui cabos (mouse, teclado, fones)
- **Arquitetura mestre/escravo:** Um dispositivo controla, outros pedem permissão para transmitir

### WiMAX (802.16)

**Características:**
- WiFi de longa distância (~10 km)
- ~14 Mbps
- Usa estações base com antenas direcionais
- "WiFi da cidade" em vez de "WiFi da casa"

---

## Resumo dos Resumos

A Camada Física transforma seus dados em sinais (elétricos, luminosos ou de rádio) que podem viajar. Esses sinais podem ser analógicos (variação contínua) ou digitais (0 e 1). Durante a viagem, enfrentam problemas como ruído, atenuação e distorção. 

Existem vários meios físicos: cabos de cobre (par trançado - mais comum hoje), fibra óptica (melhor desempenho, mais cara) e wireless (sem fio - mais conveniente). Cada um tem suas vantagens e limitações de velocidade, distância e custo.

O desempenho depende de largura de banda (capacidade), latência (tempo) e da qualidade do meio físico usado. Quanto mais moderno o cabo ou padrão wireless, maior a velocidade e distância alcançadas.