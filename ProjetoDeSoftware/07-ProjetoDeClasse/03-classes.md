# Resumo Refinamento de Diagrama de Classes

## Modelo de Domínio vs Diagrama de Classe de Projeto

| **Modelo de Domínio** | **DCP (Projeto)** |
|------------------------|-------------------|
| Conceitual (mundo real) | Especificação de software |
| Análise | Design/Implementação |
| Sem detalhes técnicos | Com métodos, navegabilidade, dependências |

**Analogia**: Modelo de Domínio é o **mapa turístico** (conceitos gerais). DCP é o **manual de construção** (detalhes para implementar).

---

## Refinamentos no DCP

O DCP adiciona ao Modelo de Domínio:
✅ **Detalhamento** de atributos e operações  
✅ **Métodos** (não apenas responsabilidades)  
✅ **Navegabilidade** nas associações  
✅ **Dependências** explícitas  
✅ **Interfaces** e contratos  
✅ **Visibilidade** (public, private, protected)  
✅ **Padrões de projeto** aplicados  

---

## Tipos de Relacionamentos

### 1. **Associação** 🔗
Relacionamento **estrutural** entre instâncias (conexão permanente).

**Quando usar**: Um atributo não é tipo primitivo → é associação.

```java
class Cliente {
    private Endereco endereco; // Associação!
}
```

**Tipos especiais**:
- **Agregação** (◇): "parte de" (partes podem existir sozinhas)
- **Composição** (◆): "parte de" forte (partes morrem com o todo)

**Exemplo Composição**: Pedido ◆─ ItemPedido (item não existe sem pedido)

---

### 2. **Navegabilidade** 🧭
Define a **direção** da comunicação entre objetos.

**Por padrão**: Bidirecional (ambos se conhecem)  
**No projeto**: Definir navegabilidade unidirecional quando possível (↓ acoplamento)

```
Cliente ──> Pedido  (Cliente conhece Pedido, mas não vice-versa)
```

**Como identificar**:
- Explorar **diagramas de interação**
- Se A envia mensagem para B → navegabilidade A → B
- Se A cria B → navegabilidade A → B

---

### 3. **Dependência** ⚡
Relacionamento **não estrutural** (temporário, transiente).

**Representação**: Linha tracejada `- - - >`

**Quando ocorre**:
- Classe usa serviços de outra temporariamente
- Parâmetro de método, variável local, retorno de método

```java
class Relatorio {
    public void gerar(Cliente cliente) { // Dependência!
        // usa cliente temporariamente
    }
}
```

---

## Tipos de Visibilidade (Como objetos se "enxergam")

### **1. Visibilidade de Atributo** (Associação)
B é atributo de A → **permanente**

```java
class Loja {
    private Registro registro; // Visibilidade permanente
}
```

---

### **2. Visibilidade por Parâmetro** 
B é passado como parâmetro → **temporária**

```java
class Emprestimo {
    public void processar(Cliente c) { // c visível aqui
        // usa c
    } // c não é mais visível
}
```

---

### **3. Visibilidade Local**
B é criado/retornado dentro de método → **temporária**

```java
class Loja {
    public void criarVenda() {
        Venda v = new Venda(); // Visível apenas aqui
        // ou
        Produto p = catalogo.buscar(); // Retorno de método
    }
}
```

---

### **4. Visibilidade Global**
B é acessível globalmente → **permanente** (evitar!)

**Alternativa**: Use padrão **Singleton**.

---

### **5. Visibilidade de Classe** (Estática)
A chama método estático de B

```java
class Loja {
    public void contar() {
        Cliente.getQuantidade(); // Método estático
    }
}
```

---

## Associação vs Dependência

| **Associação** | **Dependência** |
|----------------|-----------------|
| Estrutural | Não estrutural |
| Permanente | Temporária |
| Atributo da classe | Parâmetro/local/global |
| Linha sólida | Linha tracejada |

**Regra de ouro**: No projeto, **transformar associações em dependências** quando possível (↑ encapsulamento).

**Manter como associação**:
- Entre classes de **entidade** (domínio)

**Transformar em dependência**:
- Controlador ↔ Entidade (frequentemente)
- Fronteira ↔ Controlador (geralmente)

---

## Interfaces 🎭

### O que é?
**Contrato** que força classes não relacionadas a implementarem métodos comuns.

**Objetivos**:
1. Capturar semelhanças sem forçar herança
2. Declarar operações obrigatórias
3. Revelar operações sem revelar implementação
4. **Facilitar desacoplamento**

**Analogia**: Tomada elétrica (interface) aceita qualquer plugue que siga o padrão.

### Notações

**Forma 1**: Classe com estereótipo
```
<<interface>>
ICMS
+ meuICMS(): double
```

**Forma 2**: Círculo (lollipop)
```
○─ Conta (interface fornecida)
○── (interface requerida)
```

### Exemplo
```java
interface ICMS {
    double meuICMS();
}

class Carro implements ICMS {
    public double meuICMS() { return 0.17 * preco; }
}

class Consultoria implements ICMS {
    public double meuICMS() { return 0.1 * valor; }
}
```

---

## Especificação por Tipo de Classe

### **Classes de Fronteira** 🖥️
- **NÃO** incluir lógica de negócio
- Apenas captação/apresentação de dados
- Facilita mudança de ambiente (GUI, Web, Mobile)

### **Classes de Entidade** 📦
- Núcleo do domínio
- Identificar objetos **persistentes**
- Criar identificador de implementação (ID técnico)

### **Classes de Controle** 🎮
- Coordenar casos de uso
- Conectar fronteira ↔ entidade
- Evitar baixa coesão: particionar se necessário
- **Front Controller**: ponto central de entrada (comum em Web)

---

## Implementação de Associações

**Mínimo necessário** para associações:
```java
class Cliente {
    private Pedido pedido;
    
    // SET (criar/redefinir)
    public void setPedido(Pedido p) { this.pedido = p; }
    
    // GET (obter)
    public Pedido getPedido() { return pedido; }
    
    // REMOVE (exceto 1..1)
    public void removePedido() { this.pedido = null; }
}
```

**Multiplicidade n**:
```java
class Dependente {
    private List<Cliente> clientes = new ArrayList<>();
    
    public List<Cliente> getClientes() { return clientes; }
    public void addCliente(Cliente c) { clientes.add(c); }
    public void removeCliente(Cliente c) { clientes.remove(c); }
}
```

---

## Checklist do Refinamento

✅ Definir navegabilidade (evitar bidirecional desnecessário)  
✅ Transformar associações em dependências quando possível  
✅ Adicionar interfaces para desacoplamento  
✅ Especificar visibilidade (public/private/protected)  
✅ Detalhar métodos e operações  
✅ Aplicar padrões GRASP  
✅ Separar responsabilidades (Fronteira/Controle/Entidade)  
✅ Criar classes auxiliares se necessário (Invenção Pura)  

---

## Princípios-Chave

🎯 **Navegabilidade unidirecional** sempre que possível  
🎯 **Dependência > Associação** (quando temporário)  
🎯 **Interfaces** para contratos e desacoplamento  
🎯 **Fronteira sem lógica**, Entidade com domínio, Controle coordenando  
🎯 **Alta coesão, baixo acoplamento** (sempre!)  

> **Lembre-se**: DCP é o blueprint para os programadores implementarem. Seja específico, mas não exagere!