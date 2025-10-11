# 📚 Endereçamento IP

## Introdução

O **endereçamento IP** é usado na camada de rede para identificar de forma única cada dispositivo em uma rede, permitindo que os pacotes de dados cheguem ao destino correto. Atualmente, o **IPv4** é o protocolo mais usado, mas devido à escassez de endereços, estamos em transição para o **IPv6**, que oferece um espaço muito maior de endereços.

---

## 🔢 Endereçamento IPv4

### Formato do IPv4
- Possui **32 bits**, divididos em **4 octetos** de 8 bits cada.
- Representado em decimal: **ex: 192.168.0.1**
- Exemplo em binário:  
  `192.168.0.1` = `11000000.10101000.00000000.00000001`

### Rede e Host
- Parte do endereço identifica a **rede** (como a rua) e outra parte identifica o **host** (como a casa).
- Exemplo:  
  - Rede: `200.243.217.0`  
  - Hosts: `200.243.217.1` a `200.243.217.254`  
  - Broadcast: `200.243.217.255`

### Tipos de Endereços IPv4
- **Rede**: bits de host em 0 → `200.243.217.0`
- **Host**: endereços das máquinas → `200.243.217.1` a `.254`
- **Broadcast**: bits de host em 1 → `200.243.217.255`

### Classes de Endereços
- **Classe A**: primeiro bit `0` → redes grandes
- **Classe B**: primeiros bits `10` → redes médias
- **Classe C**: primeiros bits `110` → redes pequenas
- **Classe D**: multicast
- **Classe E**: experimental

👉 **Problema**: As classes levam a desperdício de IPs. Ex: uma empresa com 300 máquinas teria que usar uma classe B (65 mil IPs) ou duas classes C (508 IPs).

---

## 🛠️ Máscara de Rede e CIDR

### O que é a Máscara?
- Indica quantos bits são da **rede** e quantos são do **host**.
- Formas de representar:
  - Binário: `11111111.11111111.11111111.00000000`
  - Decimal: `255.255.255.0`
  - CIDR: `/24`

### Operação AND
- Usada para verificar se dois IPs estão na mesma rede:
  - Ex:  
    `192.168.0.1` AND `255.255.255.0` = `192.168.0.0`  
    `192.168.1.1` AND `255.255.255.0` = `192.168.1.0` → redes diferentes!

### CIDR (Classless Inter-Domain Routing)
- Permite quebras flexíveis, não apenas /8, /16, /24.
- Exemplo: `/27` = `255.255.255.224` → 30 hosts úteis (2⁵ – 2)
- Divisão de uma rede Classe C em 8 sub-redes com /27:
  - Empresa 1: `200.30.40.0/27` (hosts: .1 a .30)  
  - Empresa 2: `200.30.40.32/27` (hosts: .33 a .62)  
  - …  
  - Empresa 8: `200.30.40.224/27` (hosts: .225 a .254)

---

## 🔄 NAT – Network Address Translation

### O que faz?
- Traduz IPs **privados** (inválidos na Internet) para IPs **públicos** (válidos).

### IPs Privados Reservados
- `10.0.0.0/8`
- `172.16.0.0/12`
- `192.168.0.0/16`

### Vantagens do NAT
- Economia de IPs públicos
- Segurança: esconde a rede interna
- Flexibilidade: mudança de provedor sem alterar toda a rede

---

## ⚠️ Endereços IPv4 Reservados

- `0.0.0.0` → roteamento padrão
- `127.0.0.1` → loopback (teste local)
- `169.254.0.0/16` → link local (sem DHCP)
- `192.0.2.0/24` → testes e documentação

---

## 🌐 Endereçamento IPv6

### Formato do IPv6
- **128 bits**, representados em hexadecimal.
- Exemplo: `2001:0db8:85a3::8a2e:0370:7334`
- Abreviação:  
  `FE00:0000:0000:0001:0000:0000:0000:0056` → `FE00::1:0:0:0:56` ou `FE00:0:0:1::56`

### Prefixos IPv6
- Notação: `endereço/tamanho_do_prefixo`  
  Ex: `2001:db8:3003:2::/64`
- Hierárquico, otimiza roteamento.

### Tipos de Endereços IPv6
- **Unicast**: ponto a ponto (ex: Global Unicast)
- **Anycast**: um para o mais próximo de muitos
- **Multicast**: um para muitos (substitui o broadcast do IPv4)

### Endereços Especiais IPv6
- `::1` → loopback
- `::0` → não especificado
- `::FFFF:192.168.100.1` → IPv4 mapeado

### Sub-redes IPv6
- Tamanho padrão: `/64` → 2⁶⁴ hosts por sub-rede!
- Recomendações NIC.br:
  - `/64` a `/56` → usuários domésticos
  - `/48` → empresas

---

## 🔁 Migração do IPv4 para o IPv6

### Técnicas de Transição
- **Pilha Dupla (Dual Stack)**: dispositivos rodam IPv4 e IPv6 ao mesmo tempo.
- **Tunelamento**:  
  - **6over4**: encapsula IPv6 em IPv4  
  - **4over6**: encapsula IPv4 em IPv6

👉 Objetivo: permitir uma transição gradual até que o IPv6 seja dominante.

---

## ✅ Resumo Final

| Aspecto               | IPv4                          | IPv6                            |
|-----------------------|-------------------------------|----------------------------------|
| Bits / endereços      | 32 bits ~ 4,3 bi             | 128 bits ~ 3,4 x 10³⁸           |
| Formato               | Decimal (192.168.0.1)        | Hexadecimal (2001:db8::1)       |
| Máscara / CIDR        | Sim, com /24, /27, /30       | Sim, com /64, /48, /56          |
| Broadcast             | Sim                           | Não → substituído por Multicast |
| Endereços privados    | 10.0.0.0, 172.16.0.0, 192.168.0.0 | Unique-Local (FD00::/8)     |
| NAT                   | Necessário para economia      | Menos necessário                |
| Transição             | –                             | Pilha dupla e tunelamento       |

O **IPv4** ainda é amplamente usado, mas o **IPv6** veio para resolver a escassez de endereços e melhorar a eficiência do roteamento. Com o **CIDR** e o **NAT**, prolongamos a vida do IPv4, mas a migração para o IPv6 é inevitável e já está em andamento! 🚀

---  