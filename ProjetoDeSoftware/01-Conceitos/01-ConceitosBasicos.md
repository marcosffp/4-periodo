### **Conceitos Básicos de Projeto de Software**

#### **1. Abstração**  
- **Definição:** Isolar aspectos relevantes de um sistema, ignorando detalhes irrelevantes para o contexto atual.  
- **Tipos:**  
  - **Procedural (Funcional):** Oculta **como** uma tarefa é realizada, expondo apenas **o que faz** (ex.: função `abrir()`).  
  - **De Dados:** Oculta a estrutura interna dos dados, expondo apenas operações para manipulá-los (ex.: objeto `Porta` com atributos ocultos).  
- **Objetivo:** Reduzir complexidade, permitindo focar em níveis hierárquicos de detalhamento.  

---

#### **2. Arquitetura de Software**  
- **Definição:** Organização estrutural do sistema em componentes, suas interações e princípios de integridade conceitual.  
- **Propósito:** Garantir coerência, manutenibilidade e escalabilidade.  
  - Exemplo: Divisão em camadas (apresentação, negócio, dados).  

---

#### **3. Padrões de Projeto**  
- **Origem:** Inspirados em Christopher Alexander (arquitetura civil), adaptados para software por Gamma et al. (1995).  
- **Função:** Soluções reutilizáveis para problemas recorrentes (ex.: Singleton, Observer).  
- **Frase-chave:**  
  > *"Um padrão descreve um problema e sua solução, aplicável milhões de vezes."*  

---

#### **4. Separação por Interesse**  
- **Princípio:** Dividir sistemas complexos em partes com responsabilidades únicas.  
- **Vantagens:**  
  - Facilita desenvolvimento, testes e evolução.  
  - Exemplo: Separar lógica de negócio da interface do usuário.  

---

#### **5. Modularidade**  
- **Conceito:** Aplicação prática da separação por interesse, criando módulos independentes.  
- **Analogia:** Limitação cognitiva humana → compreender partes menores é mais eficiente.  
- **Relação com Abstração:**  
  > *"A abstração define o propósito do módulo; a modularidade organiza sua implementação."*  

---

#### **6. Ocultação de Informação (Encapsulamento)**  
- **Definição:** Esconder detalhes internos de um módulo, expondo apenas interfaces controladas.  
- **Benefícios:**  
  - Reduz acoplamento entre componentes.  
  - Protege dados e algoritmos de acessos indevidos.  
- **Exemplo:** Classe `ContaBancária` que oculta saldo e expõe apenas `depositar()` e `sacar()`.  

---

### **Síntese dos Conceitos**  
| **Conceito**               | **Objetivo Principal**                  | **Exemplo Prático**                |  
|----------------------------|----------------------------------------|------------------------------------|  
| **Abstração**              | Simplificar problemas complexos        | Função `calcularImposto()` sem expor fórmula. |  
| **Arquitetura**            | Organizar componentes com coerência    | Microsserviços em aplicações web.  |  
| **Padrões**                | Reutilizar soluções eficazes           | Usar Factory Method para criar objetos. |  
| **Separação por Interesse**| Dividir responsabilidades              | MVC (Model-View-Controller).       |  
| **Modularidade**           | Facilitar manutenção e escalabilidade  | Módulo `autenticação` separado.    |  
| **Ocultação de Informação**| Proteger detalhes de implementação     | Atributos privados em POO.         |  

**Princípio Central:**  
> *"Projetar software é gerenciar complexidade através da organização lógica e do ocultamento estratégico de detalhes."*  

