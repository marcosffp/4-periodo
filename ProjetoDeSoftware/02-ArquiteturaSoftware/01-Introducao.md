# Introdução à Arquitetura de Software

## 📌 O que é Arquitetura no Contexto da Computação?

A arquitetura, no contexto da computação, preocupa-se com **"as coisas importantes"** (Ralph Johnson). Isso inclui:

- O **design e a estrutura** de um sistema computacional.
- A interação entre seus componentes, sejam de **hardware ou software**.

### Exemplo: Arquitetura de Processadores
- **CISC (Complex Instruction Set Computer)**: Instruções complexas, cada uma executando múltiplas operações de baixo nível.
- **RISC (Reduced Instruction Set Computer)**: Instruções simples e padronizadas, buscando eficiência e velocidade.

Ambas são **decisões arquiteturais** fundamentais que impactam o desempenho e a complexidade do sistema.

---

## 💻 O que é Arquitetura de Software?

Existem múltiplas definições, mas duas se destacam:

### Definição 1: Foco em Componentes de Alto Nível
- A arquitetura preocupa-se com **unidades maiores** que classes: módulos, subsistemas, serviços, etc.
- Esses componentes devem ser **relevantes para os objetivos do sistema**.

#### Exemplo Prático:
- Em um **sistema de informação**, o módulo de persistência (que acessa o banco de dados) é **fundamental** → Faz parte da arquitetura.
- Em um **sistema de diagnóstico por IA**, o módulo de persistência é **secundário** → Não faz parte da arquitetura principal.

### Definição 2: Decisões Importantes e Difíceis de Reverter (Ralph Johnson)
- A arquitetura é o conjunto de **decisões críticas** que moldam o sistema.
- Exemplos:
  - Escolha da linguagem de programação.
  - Escolha do banco de dados (MySQL vs MongoDB).
  - Estilo arquitetural (microsserviços vs monolítico).

#### Exemplo Histórico: Debate Tanenbaum vs Torvalds
- **Andrew Tanenbaum**: Defendia **microkernels** (núcleos mínimos e modulares).
- **Linus Torvalds**: Defendeu **kernels monolíticos** (como o Linux), que, com o tempo, tornaram-se grandes e complexos.

> “A arquitetura de software é a **espinha dorsal** de um sistema, composta por seus **componentes**, **relações** e **princípios** de projeto e evolução.”

---

## ✅ Vantagens de uma Boa Arquitetura

- **Modularidade**: Divisão clara de responsabilidades.
- **Flexibilidade**: Facilidade de adaptação e evolução.
- **Manutenibilidade**: Correções e melhorias são mais simples.
- **Testabilidade**: Componentes podem ser testados isoladamente.

---

## ❌ Riscos de uma Má Arquitetura

### Exemplo: Knight Capital Group (2012)
- Perda de **US$ 440 milhões em 45 minutos** devido a um erro de software.
- Causa: Reutilização indevida de um sinal de software, ativando código antigo e não testado.
- Consequência: Queda da empresa.

---

## 🧩 Padrões Arquiteturais

São modelos consagrados para organizar sistemas:

- **Arquitetura em Camadas**: Separação em níveis (ex: apresentação, negócio, dados).
- **MVC (Model-View-Controller)**: Separação entre lógica, interface e dados.
- **Microsserviços**: Sistemas como conjuntos de serviços independentes.
- **Orientada a Mensagens**: Comunicação assíncrona via mensagens.
- **Publish/Subscribe**: Componentes se inscrevem para receber eventos.

---

## ⚠️ Anti-Padrões Arquiteturais

### Big Ball of Mud (Grande Bola de Lama)
- Sistema **sem arquitetura definida**.
- **Dependências caóticas** entre módulos (como um espaguete).
- **Manutenção difícil e arriscada**.

#### Caso Real: Sistema Bancário (IEEE Software, 2009)
- Cresceu de 2,5M para 25M de linhas de código.
- Diretório com **15 mil arquivos**.
- Tempo de onboarding de novos engenheiros: de 3 para 7 meses.
- Correções frequentemente introduziam novos bugs.

> **Conclusão:** Sistemas assim são mais comuns do que imaginamos!

---

## 🔍 Projeto vs. Arquitetura

- **Projeto de Arquitetura**:
  - Nível **macro**.
  - Define componentes e suas interações.
  - Foca em **requisitos de qualidade** (desempenho, segurança, etc.).

- **Projeto Detalhado**:
  - Nível **micro**.
  - Define classes e colaborações.
  - Foca em **requisitos funcionais**.

---

## 👥 Stakeholders no Processo Arquitetural

- **Analista de Requisitos**: Identifica o que o sistema deve fazer.
- **Arquiteto de Software**: Projeta a arquitetura.
- **Desenvolvedor**: Implementa os componentes.
- **Cliente/Usuário**: Define necessidades e expectativas.
- **Testador**: Garante a qualidade.

---

## 🧠 O Arquiteto de Software

### Habilidades Necessárias:
- Domínio profundo do negócio e da tecnologia.
- Conhecimento de modelagem e metodologias.
- Visão estratégica e competitiva.

### Tarefas Principais:
- Especificar a arquitetura com base nos requisitos.
- Modelar e prototipar.
- Analisar trade-offs e viabilidade.
- Accompanyar tendências tecnológicas.

---

## ✅ Conclusão

A arquitetura de software é **fundamental** para o sucesso de sistemas complexos. Ela vai além da codeção – é sobre **tomar decisões inteligentes** que garantam **qualidade, manutenibilidade e evolução**.

> Uma boa arquitetura não impede problemas, mas torna mais fácil resolvê-los. Uma má arquitetura é um problema sem solução fácil.

