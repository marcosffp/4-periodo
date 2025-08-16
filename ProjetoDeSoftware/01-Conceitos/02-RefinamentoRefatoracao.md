### **Conceitos Avançados de Projeto de Software**

#### **1. Independência Funcional**  
- **Definição:** Capacidade de um módulo funcionar com mínima dependência de outros componentes.  
- **Baseia-se em:**  
  - **Separação por interesses** (responsabilidades únicas)  
  - **Modularidade** (divisão em partes independentes)  
  - **Encapsulamento** (ocultação de detalhes internos)  
- **Critérios de Avaliação:**  
  - **Coesão Alta (Desejável):** Módulo executa **uma única tarefa** de forma robusta.  
  - **Acoplamento Baixo (Desejável):** Mínima interdependência entre módulos.  

**Exemplo Prático:**  
- Um módulo `Autenticação` coeso (só valida credenciais) e com baixo acoplamento (usa interface padrão como JWT).  

---

#### **2. Acoplamento**  
- **Tipos Comuns (do Menos ao Mais Problemático):**  
  1. **Dados:** Módulos compartilham apenas dados (ex.: parâmetros em funções).  
  2. **Controle:** Um módulo controla a lógica de outro (ex.: callbacks).  
  3. **Conteúdo:** Módulo acessa dados internos de outro (viola encapsulamento).  
- **Objetivo:** Minimizar acoplamento para facilitar manutenção e escalabilidade.  

**Comparativo:**  
| **Tipo de Acoplamento** | **Impacto**                          |  
|--------------------------|--------------------------------------|  
| Dados                    | Baixo risco (ideal)                  |  
| Controle                 | Moderado (exige cuidado)             |  
| Conteúdo                 | Alto risco (evitar)                  |  

---

#### **3. Refinamento**  
- **Estratégia:** Abordagem **top-down** para detalhar progressivamente um sistema.  
- **Processo:**  
  1. **Nível Alto:** Descrição conceitual (ex.: "Processar pagamento").  
  2. **Níveis Intermediários:** Detalhamento de etapas (validação, gateway).  
  3. **Nível Baixo:** Implementação em código.  
- **Relacionamento com Abstração:**  
  > *"Abstração oculta detalhes; refinamento os revela gradualmente."*  

**Exemplo:**  
- De "Calcular imposto" → fórmula matemática → código em Python.  

---

#### **4. Refatoração**  
- **Definição:** Reestruturação de código **sem alterar comportamento externo**, visando:  
  - Melhorar legibilidade.  
  - Reduzir complexidade.  
  - Facilitar manutenção.  
- **Tipos Comuns:**  
  - **Extrair Método:** Dividir funções longas.  
  - **Substituir Condicional por Polimorfismo:** Eliminar `if-else` complexos.  
- **Leis de Lehman:**  
  - Sistemas degradam-se sem manutenção contínua.  
  - Refatoração combate a "entropia de software".  

**Cenário Típico:**  
- Antes: Função `processarPedido()` com 200 linhas.  
- Depois: Dividida em `validarDados()`, `calcularTotal()`, `enviarConfirmacao()`.  

---

### **Síntese dos Conceitos**  
| **Conceito**               | **Objetivo**                          | **Ferramenta/Prática**               |  
|----------------------------|---------------------------------------|---------------------------------------|  
| **Independência Funcional**| Minimizar dependências entre módulos  | Alta coesão + baixo acoplamento       |  
| **Refinamento**            | Detalhar sistemas complexos           | Abordagem top-down                    |  
| **Refatoração**            | Manter código sustentável             | Extração de métodos, polimorfismo     |  

**Princípio Central:**  
> *"Bom software é como Lego: módulos independentes que se encaixam sem cola."*  

