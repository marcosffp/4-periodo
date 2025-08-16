### **O que é NAT (Network Address Translation)?**  
É um "tradutor" que converte endereços **privados** (da sua rede local) em um endereço **público** (o IP que a internet enxerga).  

Exemplo rápido com o que você enviou:  
- Seu roteador tem um IP público como **200.221.4.1** (um dos IPs da sua imagem).  
- Dentro da sua casa, seus dispositivos usam IPs privados (como **192.168.1.100**).  
- O NAT pega esses IPs privados e os "esconde" atrás do IP público quando você acessa algo (como `www.mit.edu`).  

---

### **Onde ele fica?**  
- **No seu roteador**: Seja da operadora (Claro, Vivo, etc.) ou um roteador comum.  
- **Vem de fábrica**: Sim! Você não precisa configurar nada – já funciona automaticamente.  

---

### **Como funciona?**  
1. Você digita `www.mit.edu` no celular (IP privado: **192.168.1.100**).  
2. O NAT do roteador:  
   - Troca **192.168.1.100** pelo IP público (**200.224.4.1**).  
   - Guarda uma "tabela" para saber que *esse* celular fez a requisição.  
3. Quando o site responde, o NAT envia a resposta de volta para o celular certo.  

---

### **Por que existe?**  
1. **Economia de IPs**: Só seu roteador precisa de um IP público (não todos os dispositivos da sua casa).  
2. **Segurança**: Esconde seus dispositivos da internet (só o roteador é visível).  
3. **Organização**: Permite que vários dispositivos usem a mesma internet.  

---

### **Resumo visual**  
```
[Seu celular] → (NAT no roteador) → [Internet (www.mit.edu)]  
  192.168.1.100      200.221.4.1  
```  
O NAT é o "meio de campo" que faz essa tradução sem você perceber.  

