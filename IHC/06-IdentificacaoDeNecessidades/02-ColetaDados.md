### Técnicas de Identificação de Necessidades dos Usuários em IHC

Este documento complementa a primeira parte sobre identificação de necessidades, detalhando as **técnicas de coleta de dados** e como aplicá-las efetivamente no processo de design de Interação Humano-Computador (IHC).

#### **1. Como Coletar Dados dos Usuários: Visão Geral das Técnicas**
A fase de identificação de necessidades utiliza um conjunto diversificado de técnicas para obter uma compreensão profunda dos usuários, seu contexto, tarefas e objetivos. As principais técnicas abordadas são:
*   **Entrevistas**
*   **Grupos de Foco**
*   **Questionários**
*   **Brainstorming de Necessidades e Desejos**
*   **Classificação de Cartões (Card Sorting)**
*   **Estudos de Campo** (incluindo a **Investigação Contextual**)

Cada método possui vantagens, desvantagens e contextos de aplicação ideais, sendo comum a utilização de **triangulação** (combinação de técnicas) para validar e aprofundar os resultados.

#### **2. Grupo de Foco**
Um **Grupo de Foco** é uma discussão ou entrevista coletiva guiada por um moderador experiente, envolvendo geralmente de **3 a 10 participantes** por uma ou duas horas.

*   **Objetivo e Vantagem:** Permite obter, em pouco tempo, **múltiplos pontos de vista** e percepções de um grupo. A interação entre os participantes pode gerar insights que não surgiriam em entrevistas individuais.
*   **Papel do Moderador:** É crucial. Deve garantir que todos participem, evitando que pessoas extrovertidas dominem a discussão e incentivando a contribuição de participantes mais quietos ou tímidos.
*   **Questões Típicas:** As discussões geralmente giram em torno de um "dia típico" do usuário, tarefas realizadas, terminologia do domínio, preferências, aversões, objetivos e reações a conceitos ou protótipos de produtos.
*   **Uso de Protótipos:** É comum fornecer materiais concretos ou protótipos para os participantes interagirem e darem feedback com um foco bem definido.
*   **Cuidados:** Deve-se evitar tópicos polêmicos (como política ou valores morais) para manter o foco no objetivo do produto.

#### **3. Questionários**
Questionários são **formulários com perguntas** a serem respondidas por um grande número de pessoas.

*   **Objetivo e Vantagem:** Permitem coletar dados **rapidamente e em grande escala**, de forma relativamente barata. São ideais para obter dados quantitativos e estatisticamente significativos.
*   **Desvantagem:** Tendem a ser **menos detalhados e profundos** compared to interviews and focus groups. Requerem cuidado extremo na elaboração para evitar perguntas ambíguas ou que induzam respostas.
*   **Tipos de Perguntas:**
    *   **Fechadas:** Escolha de uma ou mais opções predefinidas, faixas de valores (ex.: idade, renda).
    *   **Ordenação:** Priorizar itens por ordem de preferência.
    *   **Escala Likert:** Medir o nível de concordância com uma afirmação (ex.: Concordo Plenamente, Discordo Totalmente).
    *   **Diferencial Semântico:** Avaliar um conceito usando adjetivos opostos em uma escala (ex.: Útil |___|___|___|___| Inútil).
    *   **Abertas:** Permitem respostas livres, mas devem ser usadas com moderação para não reduzir a taxa de resposta.
*   **Recomendações para Elaboração:**
    *   **Simplicidade e Clareza:** Perguntas devem ser simples, concisas, diretas e conter apenas um conceito.
    *   **Neutralidade:** Não devem induzir o respondente.
    *   **Ordem Lógica:** Perguntas gerais antes das específicas; agrupar perguntas por tópicos.
    *   **Opções de Resposta:** Incluir opções neutras como "não sei" ou "outro" e evitar sobreposição em faixas de valores (ex.: 1-3 horas e 3-5 horas criam ambiguidade para quem responde 3).
*   **Uso Complementar:** Frequentemente usados em conjunto com entrevistas. Os questionários podem **corroborar resultados qualitativos** das entrevistas com dados quantitativos. Se os resultados do questionário forem inesperados, novas entrevistas podem investigar os motivos.
*   **Questionários Validados:** Existem instrumentos já validados pela comunidade, como:
    *   **SUS (System Usability Scale):** Mede usabilidade percebida. O score é calculado e convertido para uma escala de 0-100 (média é 68, acima de 80 é considerado excelente).
    *   **QUIS (Questionnaire for User Interaction Satisfaction)**
    *   **ASQ (After Scenario Questionnaire)**
    *   **TAM (Technology Acceptance Model):** Mede a percepção de utilidade e facilidade de uso.
    *   **UEQ (User Experience Questionnaire)**
    *   **SAM (Self Assessment Manikin):** Mede reações emocionais (prazer, excitação, dominância).

#### **4. Brainstorming de Necessidades e Desejos dos Usuários**
Esta técnica busca levantar de forma **livre e criativa** um conjunto amplo de opiniões sobre o que os usuários querem e precisam em um produto.

*   **Diferença para Grupo de Foco:** Enquanto o grupo de foco busca responder perguntas específicas, o *brainstorming* é mais exploratório e aberto, focando na geração de ideias sem julgamento.
*   **Processo:** Envolve geralmente de **2 a 12 usuários** orientados por um **moderador**. A sessão começa com uma pergunta aberta sobre o "sistema ideal", que pode se focar em:
    1.  **Informações:** "Que informações o sistema ideal deve fornecer?"
    2.  **Tarefas:** "Que tarefas você gostaria de realizar com o sistema ideal?"
    3.  **Características:** "Que características (ex.: confiabilidade, segurança) o sistema ideal deve ter?"
*   **Papel do Moderador:** Deve garantir um ambiente livre de censura, manter o foco no objetivo, motivar a participação de todos, fazer perguntas para clarificar ideias e evitar influenciar as respostas com suas próprias opiniões.
*   **Análise e Consolidação:** Uma técnica comum é usar **Diagramas de Afinidade**. As ideias são escritas em post-its, agrupadas pelos participantes com base na similaridade e, em seguida, rotuladas. Isso ajuda a organizar e priorizar as necessidades identificadas.
*   **Resultado:** A lista gerada alimenta diretamente a especificação de requisitos e o design, podendo também ajudar a *reduzir* funcionalidades desnecessárias que nunca foram mencionadas pelos usuários.

#### **5. Classificação de Cartões (Card Sorting)**
É um método usado para **descobrir como os usuários organizam mentalmente a informação**, ajudando a definir a arquitetura de informação de um sistema (ex.: estrutura de menus, organização de conteúdo em um site).

*   **Processo:** Participantes recebem cartões com conceitos, itens de conteúdo ou funcionalidades e são instruídos a agrupá-los de forma que faça sentido para eles.
*   **Tipos:**
    *   **Aberta:** Os participantes criam e nomeiam seus próprios grupos. É exploratória e revela o modelo mental dos usuários.
    *   **Fechada:** Os participantes classificam os cartões em categorias predefinidas. É usada para validar ou refinar uma estrutura existente.
*   **Aplicação dos Resultados:** Os resultados mostram como os usuários esperam encontrar a informação, mas **não definem cegamente a arquitetura final**. O designer deve sintetizar esses dados com os objetivos do produto, análise de conteúdo e outros findings. A atividade testa a descoberta de informação a partir do conteúdo (bottom-up), mas não testa diretamente se o usuário encontrará algo a partir de uma categoria (top-down).
*   **Logística:** Requer cuidado na seleção do conteúdo dos cartões (deve ser representativo e evitando termos que induzam a categorias). Sessões em grupo podem ser produtivas, mas o moderador deve evitar a dominação por um participante. Recomenda-se um **estudo-piloto** e um **número maior de participantes** (em torno de 15) compared to usability tests para obter resultados confiáveis.

#### **6. Estudos de Campo e Investigação Contextual**
**Estudos de Campo** envolvem observar e interagir com os usuários **em seu ambiente natural** (casa, trabalho), em contraste com ambientes controlados de laboratório.

*   **Vantagem Principal:** **Validade ecológica**. Permite entender o **comportamento real** do usuário, capturando contextos cruciais como interrupções, distrações, ferramentas auxiliares e práticas de trabalho que muitas vezes são omitidas ou não percebidas em entrevistas.
*   **Formas de Estudo:**
    *   **Observação Pura:** Observador não interage.
    *   **Observação Participante:** Observador interage e participa das atividades.
    *   **Entrevistas no Ambiente:** Combina observação com entrevistas no local.
    *   **Diários de Atividades:** Usuários registram suas atividades ao longo do tempo (observação indireta).
    *   **Investigação Contextual:** Uma forma profunda e estruturada de estudo de campo.

#### **7. Investigação Contextual**
A Investigação Contextual é uma abordagem específica de estudo de campo que aplica o **modelo Mestre-Aprendiz** para entender o trabalho real dos usuários.

*   **Princípio Fundamental:** O pesquisador (aprendiz) vai até o local do usuário (mestre) para aprender sobre seu trabalho **enquanto ele é realizado**. O foco está em tornar explícito o **conhecimento tácito** – aquele que é subjetivo, baseado na experiência e difícil de ser formalizado ou explicado.
*   **Quatro Princípios Básicos:**
    1.  **Contexto:** Ir até o local onde o trabalho acontece.
    2.  **Parceria:** Estabelecer uma relação de colaboração com o usuário.
    3.  **Interpretação:** O pesquisador compartilha suas interpretações e o usuário as corrige e refina, construindo um entendimento comum.
    4.  **Foco:** A investigação é guiada por um objetivo claro (ex.: entender tarefas específicas, fluxos de trabalho, stakeholders).
*   **Estrutura de uma Sessão (cerca de 3 horas):**
    1.  **Entrevista Convencional (15 min):** Apresentações e visão geral do trabalho.
    2.  **Transição:** Explicação da mudança para o modo observacional.
    3.  **Entrevista Contextual (main part):** O usuário executa seu trabalho enquanto o pesquisador observa, pergunta, faz anotações e coleta artefatos (objetos usados no trabalho). A conversa foca no trabalho em si, não em ideias de design.
    4.  **Conclusão:** O pesquisador sumariza o que aprendeu para validação e refinamento pelo usuário.
*   **Pós-Sessão:** A equipe de design se reúne para interpretar coletivamente os dados ricos coletados.

#### **8. Comparação e Conclusão**
Cada técnica de coleta de dados tem seu lugar no processo de design:
*   **Entrevistas** fornecem profundidade.
*   **Questionários** fornecem amplitude.
*   **Grupos de Foco** exploram dinâmicas de grupo.
*   **Brainstorming** gera ideias criativas.
*   **Card Sorting** estrutura a informação.
*   **Estudos de Campo e Investigação Contextual** revelam a realidade contextual do usuário.

A escolha da(s) técnica(s) depende dos **objetivos da coleta**, dos **recursos disponíveis** (tempo, orçamento) e do **estágio do projeto**. A combinação inteligente dessas métodos é a chave para uma compreensão holística e robusta das necessidades dos usuários, fundamentando decisões de design centradas no humano.
