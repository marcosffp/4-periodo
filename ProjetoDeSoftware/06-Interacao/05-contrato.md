# Modelagem Funcional com Contratos: Uma Explicação Completa

O conceito de **Modelagem Funcional com Contratos** é uma técnica de análise e projeto de software que visa descrever o comportamento de um sistema de forma **precisa, não ambígua e verificável**. Ele atua como uma ponte entre a descrição de alto nível do comportamento do sistema (como os Casos de Uso) e a implementação de baixo nível (o código).

O cerne desta abordagem reside na definição de **Contratos de Operação** para as ações que o sistema pode realizar.

## 1. O que são Contratos de Operação?

Um Contrato de Operação é um artefato de análise que formaliza a **intenção do usuário** ao interagir com o sistema e, mais importante, descreve os **compromissos e efeitos** que essa operação causa no estado interno do sistema.

Em essência, um contrato é composto por duas partes principais:

| Componente | Descrição | Foco |
| :--- | :--- | :--- |
| **Pré-condições** | O estado do sistema que **deve ser verdadeiro** antes que a operação possa ser executada com sucesso. | O que o sistema **espera** antes da ação. |
| **Pós-condições** | O estado do sistema **após** a execução da operação, descrevendo todas as mudanças de estado. | O que o sistema **garante** que acontecerá após a ação. |

### 1.1. Propósito e Vantagens

Os contratos de operação complementam outros artefatos de modelagem, como Casos de Uso e Diagramas de Sequência, oferecendo um **nível de precisão** que eles não alcançam.

*   **Precisão e Clareza:** Tornam explícito o efeito interno das ações do sistema, eliminando ambiguidades sobre o que muda, o que é criado ou o que é consultado.
*   **Comunicação:** Servem como um documento de referência claro para desenvolvedores e testadores, definindo o **comportamento esperado** do sistema.
*   **Estilo Declarativo:** Descrevem **o que** acontece (o resultado), e não **como** acontece (o passo a passo da implementação).

## 2. Detalhando as Pré-condições

As pré-condições definem o conjunto de regras que precisam ser satisfeitas para que uma operação seja válida. Elas garantem que a operação comece em um estado consistente.

As pré-condições podem ser classificadas em dois tipos principais:

### A. Garantia de Parâmetros (Semântica)

Verificam se os dados de entrada (parâmetros) são válidos no contexto do sistema, ou seja, se têm **significado** no modelo de domínio.

| Tipo | O que valida | Exemplo |
| :--- | :--- | :--- |
| **Sintática** | Tipo ou formato dos dados (ex: `idade` deve ser um número inteiro). | `idProduto` deve ser um número. |
| **Semântica** | Significado no contexto do sistema. | **Deve existir** um produto com o `idProduto` informado. |

### B. Restrição Complementar

Garantem que o estado atual do sistema esteja em uma situação específica e desejada antes da execução. Elas não contradizem o modelo conceitual, apenas o especializam para o contexto daquela operação.

| Tipo de Restrição | Exemplo |
| :--- | :--- |
| **Existência de Instâncias** | Deve existir um `Cliente` cujo CPF corresponda ao informado. |
| **Existência de Associação** | A operação só pode ser executada se **não existir** uma associação entre `Cliente` e `Filme` com status "em andamento". |
| **Valor de Atributo** | O atributo `saldo` do `Cliente` deve ser maior que zero. |

**Exemplo de Pré-condição:**
*Operação: FecharPedido()*
*Pré-condição: O pedido deve conter pelo menos um item e estar em status “aberto”.*

## 3. Detalhando as Pós-condições

As pós-condições descrevem as **mudanças de estado** que ocorrem nos objetos do modelo de domínio após a operação ser concluída. Elas devem ser expressas no passado, destacando o estado resultante.

As pós-condições semânticas focam em quatro tipos de modificações:

| Tipo de Modificação | Descrição | Exemplo |
| :--- | :--- | :--- |
| **Instância** | Criação ou destruição de objetos. | Uma nova instância de `Cliente` **foi criada**. |
| **Associação** | Criação ou destruição de ligações entre objetos. | O `Filme` **foi associado** ao `Cliente`. |
| **Atributo** | Modificação do valor de um atributo. | O atributo `status` do `Pedido` **foi atualizado** para “concluído”. |
| **Condicional** | Mudanças que dependem de uma condição específica. | **Se** o saldo for suficiente, o `saldo` do `Cliente` **foi decrementado**. |

**Exemplo de Pós-condição:**
*Operação: registrarCliente()*
*Pós-condição: Foi criada uma nova instância da classe `Cliente` e associada ao cadastro da `Videolocadora`.*

## 4. Quando Usar Contratos

Os contratos não são necessários para todas as operações, mas são cruciais quando o comportamento do sistema é complexo ou não é óbvio a partir de outros artefatos.

| Elabore Contratos Quando... | Evite Criar Contratos Quando... |
| :--- | :--- |
| **Muitos objetos** do domínio são criados, atualizados ou associados em um único passo. | Cada operação do sistema é **simples** ou evidente a partir do Caso de Uso. |
| A descrição do Caso de Uso **não deixa claro** quais atributos ou associações precisam ser modificados. | Os Casos de Uso já fornecem **detalhes suficientes** para a implementação. |
| Há necessidade de **extrema precisão** sobre as regras de negócio e as mudanças de estado. | A operação é uma simples consulta ou uma criação/remoção trivial de instância. |

## 5. Resumo da Relação com Outros Artefatos

A Modelagem Funcional com Contratos se encaixa perfeitamente no ciclo de desenvolvimento, refinando a análise:

1.  **Modelo Conceitual (UML):** Define a **estrutura** (classes, atributos, associações).
2.  **Casos de Uso:** Descrevem o **comportamento** do sistema do ponto de vista do usuário (o que o sistema faz).
3.  **Diagramas de Sequência:** Detalham a **sequência** de mensagens entre os objetos para realizar um Caso de Uso.
4.  **Contratos de Operação:** Descrevem o **efeito interno** e preciso de cada operação no Modelo Conceitual (como o estado muda).

Em suma, a Modelagem Funcional com Contratos é uma ferramenta poderosa para garantir que a **lógica de negócio** seja capturada de forma completa e inequívoca, servindo como um guia essencial para a implementação e para a criação de testes de software.
