# 📝 **Identificação e Documentação**

## 🔍 **Identificação de Casos de Uso**
### **Primários (Essenciais)**
São os casos de uso que representam **as funcionalidades principais** do sistema, diretamente ligadas aos objetivos dos usuários.

**Perguntas-chave para identificação:**
- Quais são as necessidades e objetivos de cada ator?
- Que informações o sistema deve produzir?
- O sistema realiza ações periódicas?
- Cada requisito funcional tem um caso de uso correspondente?

**Exemplos dos arquivos:**
- `Transferir Valores entre Contas` (sistema bancário)
- `Comparar Livro` (loja virtual)
- `Realizar Empréstimo de Livro` (biblioteca)

### **Secundários (Suporte)**
Funcionalidades de **manutenção e suporte**, necessárias mas não são o foco principal do sistema.

**Categorias típicas:**
- CRUD (Cadastros de usuários, produtos)
- Gerenciamento de acesso
- Integração com outros sistemas

**Exemplo implícito:**  
Manutenção de cadastro de clientes no sistema bancário (não descrito mas necessário)

---

## 📑 **Estrutura de Documentação de Casos de Uso**
### **Itens Básicos (Padrão Recomendado)**
| Seção               | Descrição                                                                 | Exemplo dos Arquivos                          |
|---------------------|---------------------------------------------------------------------------|-----------------------------------------------|
| **Nome**            | Verbo no infinitivo + objeto (ex: `Transferir Valores`)                   | `Comparar Livro`, `Realizar Empréstimo`       |
| **Ator Primário**   | Quem inicia a interação                                                   | `Cliente do Banco`, `Usuário da loja virtual` |
| **Fluxo Principal** | Sequência ideal de passos                                                 | Ver tabela comparativa abaixo                 |
| **Extensões**       | Cenários alternativos ou de exceção                                       | Conta incorreta, saldo insuficiente           |
| **Pré-condições**   | O que deve ser verdadeiro antes de iniciar                                | Usuário autenticado                           |
| **Pós-condições**   | Estado do sistema após execução                                           | Saldo atualizado, livro marcado como emprestado |
| **Regras de Negócio**| Restrições ou políticas                                                   | Limite de saque diário                        |

---

## 🔄 **Comparativo de Fluxos (Exemplos Práticos)**

### **1. Transferência Bancária (`Transferir Valores entre Contas`)**
| Tipo            | Descrição                                                                 |
|-----------------|---------------------------------------------------------------------------|
| **Principal**   | 1. Autenticar → 2. Informar dados → 3. Confirmar → 4. Efetivar           |
| **Extensões**   | 2a. Dados incorretos → Solicitar correção                                |
|                 | 3a. Saldo insuficiente → Notificar usuário                               |

### **2. Compra de Livros (`Comparar Livro`)**
| Tipo            | Descrição                                                                 |
|-----------------|---------------------------------------------------------------------------|
| **Principal**   | 1. Pesquisar → 2. Selecionar → 3. Fechar compra → 4. Confirmar           |
| **Extensões**   | *(Adicionar:)* 2a. Carrinho cheio → Limite máximo atingido               |
|                 | 4a. Endereço inválido → Solicitar novo endereço                          |

---

## 📊 **Tabela de Boas Práticas**

| Diretriz                        | Exemplo Correto                          | Exemplo Incorreto                     |
|---------------------------------|------------------------------------------|---------------------------------------|
| **Verbo no infinitivo**         | `Realizar Pagamento`                     | `Pagamento é realizado`               |
| **Foco no ator**                | "Usuário seleciona livro"                | "Sistema exibe livros"                |
| **Nível de detalhe**            | Máximo 9 passos no fluxo principal       | Fluxos com 15+ passos                 |
| **Separar fluxos**              | Principal vs. alternativo                | Misturar todos em um único texto      |

---
