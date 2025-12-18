# Resumo GRASP - Padrões de Projeto OO

## O que é Projeto de Classes?
Criar abstrações é como ser arquiteto de software: você decide **quais classes criar**, **quais responsabilidades** cada uma assume e **como elas se relacionam**. É difícil e vem com experiência.

### Responsabilidades
São contratos que objetos assumem:
- **Fazer**: executar ações (ex: imprimir uma venda)
- **Saber**: conhecer informações (ex: saber a data de criação)

> 💡 Responsabilidade ≠ Método. A responsabilidade é abstrata, o método a implementa.

---

## GRASP - 9 Padrões Fundamentais
**General Responsibility Assignment Software Patterns**  
Guias para atribuir responsabilidades a classes de forma inteligente.

### 1. **Especialista** 🎯
**Problema**: Quem deve fazer o quê?  
**Solução**: Quem tem a informação, faz o trabalho.

**Analogia**: Se você quer saber a média de notas da turma, pergunte à Turma, não ao Aluno individual.

```
Turma.calcularMediaIdade() ✓
Aluno.calcularMediaDaTurma() ✗
```

---

### 2. **Criador** 🏭
**Problema**: Quem cria instâncias de objetos?  
**Solução**: B cria A se:
- B contém/agrega A
- B registra A
- B usa A intensamente
- B tem dados iniciais de A

**Analogia**: A fábrica de carros cria carros, não o cliente que compra.

---

### 3. **Acoplamento Baixo** 🔗
**Problema**: Como reduzir dependências entre classes?  
**Solução**: Atribua responsabilidades minimizando conexões entre classes.

**Analogia**: Casas conectadas por cabos rígidos vs. conectadas por Wi-Fi flexível.

**Benefícios**: Mudanças em uma classe não quebram outras, facilita reuso.

---

### 4. **Controlador** 🎮
**Problema**: Quem recebe eventos do sistema (além da UI)?  
**Solução**: Uma classe que representa:
- O sistema todo (facade)
- Um caso de uso específico (TratadorDeVenda)

**Analogia**: O gerente do restaurante recebe pedidos dos garçons, não cozinha diretamente.

---

### 5. **Coesão Alta** 🎯
**Problema**: Como manter objetos focados e gerenciáveis?  
**Solução**: Cada classe tem responsabilidades relacionadas em uma área funcional.

**Níveis**:
- **Muito Baixa**: Classe faz tudo (canivete suíço)
- **Baixa**: Tarefa complexa sozinha
- **Alta**: Responsabilidades moderadas, colabora com outras ✓
- **Moderada**: Algumas áreas relacionadas

---

### 6. **Polimorfismo** 🦎
**Problema**: Como tratar alternativas baseadas em tipo?  
**Solução**: Use operações polimórficas em vez de if-else.

**Ruim**:
```
if (tipo == "Cachorro") latir();
else if (tipo == "Gato") miar();
```

**Bom**:
```
animal.emitirSom(); // cada classe implementa
```

---

### 7. **Invenção Pura** 🎨
**Problema**: E quando nenhuma classe do domínio é adequada?  
**Solução**: Invente uma classe artificial para manter coesão alta.

**Analogia**: Criar um "GerenciadorDeBancoDeDados" mesmo que não exista no mundo real.

---

### 8. **Indireção** 🔀
**Problema**: Como evitar acoplamento direto?  
**Solução**: Use uma classe mediadora entre componentes.

**Analogia**: Tradutor entre duas pessoas que falam idiomas diferentes.

---

### 9. **Variações Protegidas** 🛡️
**Problema**: Como isolar mudanças futuras?  
**Solução**: Crie interfaces estáveis em pontos de variação.

**Ferramentas**: Adaptadores, polimorfismo, interfaces abstratas.

---

## Princípios-Chave
✅ **Distribuir responsabilidades** (não concentrar tudo em uma classe)  
✅ **Alta coesão + Baixo acoplamento** = código manutenível  
✅ **Usar padrões como guia**, não regra absoluta  
✅ **Pensar em reutilização e flexibilidade**

> **Lembre-se**: Boas abstrações vêm com prática. GRASP te dá o mapa, você trilha o caminho.