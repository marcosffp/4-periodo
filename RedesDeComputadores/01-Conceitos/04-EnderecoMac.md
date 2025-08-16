### **O que é um Endereço MAC?**  
O **endereço MAC** (Media Access Control) é um **identificador único** atribuído a cada dispositivo de rede (placa de rede, Wi-Fi, celular, etc.). Ele funciona como um "CPF do hardware" e é usado para comunicação em redes locais (LAN).  

---  

### **Quem gera o endereço MAC?**  
- **Fabricantes de hardware** (como Intel, Broadcom, Qualcomm, Realtek) são responsáveis por gerar os endereços MAC.  
- A **IEEE** (Instituto de Engenheiros Eletricistas e Eletrônicos) define os padrões e distribui blocos de endereços para cada fabricante.  
- Os **6 primeiros dígitos** do MAC identificam o fabricante (ex: `00:1A:2B` é da Intel).  
- Os **6 últimos dígitos** são um número único definido pelo fabricante.  

---  

### **Quais empresas usam mais endereços MAC?**  
Empresas que produzem **muitos dispositivos de rede** têm grandes blocos de endereços MAC. Algumas das maiores:  
1. **Intel** (placas de rede)  
2. **Samsung** (celulares, smart TVs)  
3. **Apple** (iPhones, MacBooks)  
4. **Cisco** (switches, roteadores empresariais)  
5. **Huawei** (roteadores, smartphones)  

---  

### **Para que serve o MAC?**  
1. **Identificação única** na rede local (o switch usa para enviar dados corretamente).  
2. **Filtro de acesso** (redes Wi-Fi podem bloquear ou permitir dispositivos pelo MAC).  
3. **Autenticação em redes** (algumas empresas usam MAC para controle de acesso).  

---  

### **Exemplo de um endereço MAC:**  
`00:1A:2B:3C:4D:5E`  
- **00:1A:2B** → Código do fabricante (ex: Intel).  
- **3C:4D:5E** → Número único do dispositivo.  

---  

### **Posso mudar meu MAC?**  
Sim, em alguns casos é possível (**MAC spoofing**), mas geralmente o endereço original fica gravado no hardware.  

---  

### **Diferença entre IP e MAC**  

Ambos são usados para identificar dispositivos em redes, mas têm funções e características diferentes:  

| **Característica**  | **Endereço MAC** | **Endereço IP** |
|---------------------|------------------|-----------------|
| **O que identifica?** | O **hardware** (placa de rede, Wi-Fi, etc.) | O **dispositivo na rede** (pode mudar) |
| **Formato** | `00:1A:2B:3C:4D:5E` (hexadecimal) | `192.168.1.1` (IPv4) ou `2001:db8::1` (IPv6) |
| **Quem define?** | **Fabricante** (Intel, Samsung, etc.) | **Rede/Roteador** (pode ser fixo ou dinâmico) |
| **Camada de rede** | **Camada 2 (Enlace)** – Usado em redes locais (LAN) | **Camada 3 (Rede)** – Usado na internet |
| **Mudança** | **Quase imutável** (vem de fábrica) | **Pode mudar** (DHCP, VPN, redes diferentes) |
| **Uso principal** | **Comunicação local** (switch usa MAC para enviar dados) | **Roteamento global** (internet, redes externas) |

---

### **Exemplo Prático:**  
1. **Seu celular** tem um **MAC fixo** (ex: `AA:BB:CC:11:22:33`).  
2. Quando você se conecta ao Wi-Fi, o **roteador** atribui um **IP** (ex: `192.168.1.10`).  
3. Dentro de casa, o **switch** usa o **MAC** para enviar dados entre dispositivos.  
4. Na **internet**, só o **IP** é usado (o MAC não sai da sua rede local).  

---

### **Resumo:**  
- **MAC** = "CPF do hardware" (não muda, usado localmente).  
- **IP** = "endereço postal" (pode mudar, usado na internet).  