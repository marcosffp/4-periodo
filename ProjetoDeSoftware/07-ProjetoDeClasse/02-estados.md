# Resumo DTE - Diagrama de Transição de Estados

## O que é?
Descreve o **ciclo de vida** de objetos: os estados que passam e os eventos que causam mudanças. Baseado em **máquinas de estados finitos**.

**Analogia**: Como um semáforo que muda de verde → amarelo → vermelho baseado no tempo.

---

## Elementos Fundamentais

### 1. **Estados** 🎯
Situação na vida do objeto onde ele satisfaz uma condição.

**Exemplos**:
- Livro: `[Disponível]` `[Reservado]` `[Emprestado]`
- Conta: `[Ativa]` `[Bloqueada]` `[Encerrada]`

**Representação**: Retângulo arredondado  
**Estados especiais**: ● (inicial) e ◉ (final)

---

### 2. **Transições** ➡️
Mudança de um estado para outro, disparada por eventos.

**Sintaxe completa**:
```
Evento [guarda] / ação
```

**Analogia**: Clicar no botão (evento) muda a luz de apagada para acesa.

---

### 3. **Eventos** ⚡
Algo que acontece e pode mudar o estado.

**Tipos comuns**:
- **Chamada**: `finalizarPedido()`
- **Temporal**: `after(30 segundos)`
- **Mudança**: `when(saldo > 0)`

---

### 4. **Condição de Guarda** 🛡️
Condição lógica que deve ser verdadeira para transição ocorrer.

**Exemplo**:
```
Realizar saque(quantia) [quantia <= saldo] / sacar(quantia)
```
A transição só acontece se o saque for ≤ saldo.

---

## Ação vs Atividade

| Característica | **Ação** | **Atividade** |
|----------------|----------|---------------|
| **Duração** | Instantânea | Leva tempo |
| **Interrupção** | ❌ Não | ✅ Sim |
| **Onde fica** | Na seta (transição) | Dentro do estado |
| **Sintaxe** | `/nomeDaAção()` | `do/ nomeDaAtividade()` |

**Analogia**:
- **Ação**: Ligar a luz (instantâneo)
- **Atividade**: Cozinhar (pode ser interrompido)

---

## Cláusulas Especiais

### **entry** 🚪➡️
Executada **ao entrar** no estado.
```
entry/ inicializarTimer()
```

### **exit** 🚪⬅️
Executada **ao sair** do estado.
```
exit/ salvarDados()
```

### **do** 🔄
Atividade contínua **enquanto** no estado.
```
do/ tocarMúsica()
```

---

## Transições Especiais

### **Auto-transição (Loop)** 🔁
Sai e volta para o mesmo estado → **dispara entry e exit**.

### **Transição Interna** 🔒
Trata evento sem sair do estado → **NÃO dispara entry/exit**.

**Diferença crucial**:
```
Loop:     Sai (exit) → Ação → Entra (entry)
Interna:  Evento / Ação (sem sair do estado)
```

---

## Elementos Avançados

### **Pseudo Estado de Escolha** ◆
Decisão com múltiplos caminhos baseados em guardas.

**Analogia**: Roteador de pacotes que decide o caminho.

---

### **Pseudo Estado de Junção** ◆
Múltiplos caminhos convergem para um único.

---

### **Barra de Bifurcação/União** ═══
Estados operando **em paralelo** (concorrência).

**Exemplo**: Sistema tocando música E mostrando visualização simultaneamente.

---

### **Estados Compostos** 📦
Super estado contendo subestados (hierarquia).

**Benefício**: Simplifica comportamentos complexos.

**Estados Ortogonais**: Regiões paralelas dentro do super estado.

---

## Identificação de Elementos

**Fontes para identificar eventos**:
1. ✅ Descrição de casos de uso
2. ✅ Operações públicas das classes
3. ✅ Regras de negócio

**Quando criar DTE**:
- Classes com **comportamento dinâmico relevante**
- Objetos cujo **histórico precisa ser rastreado**
- Nem toda classe precisa de DTE!

---

## Exemplo Prático: Conta Bancária

```
[Ativa] --saque[saldo=quantia]/sacar()--> [Bloqueada]
       --deposito/adicionar()----------> [Ativa]
       --encerrar/finalizar()----------> [Encerrada]
```

---

## Exercício: Água 💧

Estados: `[Líquido]` `[Sólido]` `[Gasoso]` `[Plasma]`

Transições principais:
- Líquido → Sólido: `congelar()`
- Líquido → Gasoso: `evaporar()`
- Gasoso → Líquido: `condensar()`
- Gasoso → Sólido: `depositar()`
- Gasoso → Plasma: `ionizar()`
- Plasma → Gasoso: `desionizar()`

---

## Dicas Importantes

✅ **DTE = 1 classe** (não o sistema todo)  
✅ **Entry/Exit** executam em toda transição normal  
✅ **Transição interna** não dispara entry/exit  
✅ **Atividades** podem ser interrompidas, **ações** não  
✅ Use **guardas** para decisões condicionais  
✅ **Estados compostos** para hierarquia e organização

> **Lembre-se**: DTE modela o **comportamento dinâmico** ao longo do tempo, não a estrutura estática!