### Planejamento de Avaliação de IHC

#### **1. Por que Avaliar?**
A avaliação em Interação Humano-Computador (IHC) é um processo sistemático de **julgamento de valor** sobre a qualidade de uso de uma solução. Sua importância reside em:
*   **Garantia de Qualidade:** Identificar e corrigir problemas de interface e interação **antes do lançamento** do produto, assegurando um padrão mais alto de qualidade.
*   **Foco em Problemas Reais:** Permite que a equipe de desenvolvimento se concentre em resolver problemas reais dos usuários, em vez de debater preferências pessoais ou suposições.
*   **Economia de Tempo e Recursos:** Corrigir problemas de IHC durante o desenvolvimento é significativamente mais barato e rápido do que após o lançamento, reduzindo o **time-to-market** e os custos de suporte e treinamento pós-lançamento.
*   **Robustez do Produto:** Resulta em um produto final mais robusto, eficiente e satisfatório.

#### **2. Avaliação em Diferentes Perspectivas**
Um sistema deve ser avaliado sob duas perspectivas principais, que frequentemente divergem:
*   **Perspectiva de Quem Constrói (Engenharia de Software):** Foca em verificar se o sistema funciona conforme as **especificações técnicas e requisitos** definidos (testes de funcionalidade, desempenho, etc.).
*   **Perspectiva de Quem Concebe e Utiliza (Avaliação de IHC):** Foca em verificar se o sistema **apoia adequadamente os usuários** a atingirem seus objetivos em seu contexto real. Os usuários podem não compreender a lógica do designer, não julgar a solução como a melhor ou não incorporá-la em seu dia a dia.

Portanto, é **crucial avaliar do ponto de vista dos usuários**, preferencialmente com sua participação direta.

#### **3. Avaliar a Qualidade de Uso**
Avaliar a qualidade de uso vai além de testar funcionalidades. Seus benefícios são:
*   **Curto Prazo:** Aumento da produtividade dos usuários, redução na quantidade e gravidade de erros e aumento da satisfação.
*   **Médio e Longo Prazo:** Redução dos custos de treinamento e suporte técnico, e obtenção de insights valiosos para o planejamento de versões futuras do sistema.
*   Para alcançar esses benefícios, a avaliação requer um **planejamento cuidadoso** (definindo o quê, quando, onde e como avaliar), não podendo ser feita de forma improvisada.

#### **4. O que Avaliar?**
Os objetivos da avaliação devem ser claramente definidos. Os mais comuns incluem:
*   **Apropriação de Tecnologia:** Como os usuários de fato usam o sistema? Como ele impacta sua comunicação e relações? Atende às suas necessidades e desejos?
*   **Comparação de Ideias e Alternativas de Design:** Qual alternativa é mais eficiente, fácil de aprender ou preferida pelos usuários?
*   **Conformidade com Padrões:** A interface segue padrões de acessibilidade (ex.: WCAG), diretrizes do sistema operacional ou convenções do domínio?
*   **Identificação de Problemas:** O usuário consegue operar o sistema? Onde ele encontra dificuldades, comete erros ou fica insatisfeito? Ele atinge seus objetivos com eficiência?

#### **5. Quando Avaliar?**
O momento da avaliação é determinado pelo estágio de desenvolvimento e pela natureza dos dados disponíveis:
*   **Avaliação Formativa (ou Construtiva):**
    *   **Quando:** Realizada **antes** da solução estar pronta, durante o processo de design e desenvolvimento.
    *   **Objetivo:** Analisar e comparar ideias, esboços e protótipos para identificar e corrigir problemas precocemente.
    *   **Artefatos Utilizados:** Cenários, esboços de tela (*sketches*), *storyboards*, modelagens de interação e protótipos de baixa a alta fidelidade.
*   **Avaliação Somativa (ou Conclusiva):**
    *   **Quando:** Realizada **após** a conclusão da solução (ou de um protótipo de alta fidelidade).
    *   **Objetivo:** Buscar evidências de que as metas de design foram alcançadas e que o produto possui os níveis desejados de qualidade de uso.

#### **6. Onde Coletar Dados sobre Experiências de Uso?**
O local da avaliação impacta significativamente os dados coletados:
*   **Avaliação em Contexto Real de Uso:**
    *   **Vantagens:** Fornece dados ricos sobre situações típicas de uso, revelando como os usuários verdadeiramente se apropriam da tecnologia em seu ambiente natural. Captura interrupções, distrações e práticas de trabalho reais.
    *   **Desvantagens:** É difícil controlar variáveis e assegurar que aspectos específicos do sistema sejam testados.
*   **Avaliação em Laboratório:**
    *   **Vantagens:** Oferece maior controle sobre variáveis ambientais e facilita o registro de dados (gravações, *eye-tracking*). Pode variar desde uma sala de reunião simples (para grupos de foco) até um laboratório com duas salas (sala de uso e sala de observação com vidro espelhado).
    *   **Desvantagens:** Pode lack the ecological validity of a real environment, and users may behave differently knowing they are being observed.

#### **7. Que Tipos de Dados Coletar?**
Os dados a serem coletados dependem diretamente dos **objetivos** da avaliação. Exemplos:
*   **Para avaliar satisfação de necessidades:** Coletar opiniões sobre pontos fortes/fracos, grau de satisfação e necessidades de uso de outros sistemas complementares.
*   **Para identificar problemas de interação:** Coletar métricas de desempenho (taxa de conclusão de tarefas, tempo para conclusão, número e tipo de erros cometidos) e dados qualitativos (momentos de dúvida, necessidade de consulta a manuais, partes da interface que causam insatisfação).

#### **8. Métodos de Avaliação**
Os métodos de avaliação são classificados em três categorias principais:
*   **Métodos de Investigação (Inquiry):** Buscam entender as concepções, opiniões, expectativas e comportamentos dos usuários.
    *   **Exemplos:** Entrevistas, questionários, grupos de foco, estudos de campo.
*   **Métodos de Inspeção:** Especialistas examinam a interface para prever problemas de usabilidade com base em seu conhecimento e em diretrizes estabelecidas. **Não envolvem usuários reais.**
    *   **Exemplos:** Avaliação Heurística (baseada em heurísticas de Nielsen), Percurso Cognitivo, Avaliação de Comunicabilidade.
    *   **Vantagem:** Custo relativamente baixo e rápida execução.
*   **Métodos de Observação:** Envolvem observar usuários reais interagindo com o sistema para identificar **problemas reais** que eles enfrentam.
    *   **Exemplos:** Teste de Usabilidade (em laboratório ou remoto), observação em contexto real.

#### **9. Framework DECIDE**
O framework DECIDE (Sharp, Rogers e Preece, 2007) oferece um guia estruturado para planejar, executar e analisar uma avaliação:
1.  **D**eterminar os objetivos gerais da avaliação.
2.  **E**xplorar as questões específicas que a avaliação deve responder.
3.  **C**hoose (Escolher) os métodos de avaliação apropriados para cada questão.
4.  **I**dentificar e administrar as questões práticas (recursos, participantes, local, agenda).
5.  **D**ecidir como lidar com as questões éticas (consentimento, privacidade, anonimato).
6.  **E**valuate (Avaliar), interpretar e apresentar os dados coletados.

Estas atividades são interligadas e iterativas, permitindo ajustes no planejamento conforme necessário.

#### **10. Preparação da Avaliação**
Um planejamento cuidadoso é fundamental para o sucesso da avaliação. Envolve:
*   **Definição Clara:** Estabelecer objetivos, questões de pesquisa, escopo (quais partes do sistema e tarefas serão avaliadas) e escolher os métodos.
*   **Seleção de Participantes:** Recrutar de **5 a 12 usuários** que representem os perfis de usuário-alvo. Utilizar questionários screening para confirmar o perfil.
*   **Preparação de Material:** Elaborar e testar todos os materiais necessários:
    *   Termo de Consentimento Livre e Esclarecido.
    *   Questionários ou roteiros de entrevista (pré-teste e pós-teste).
    *   Cenários de tarefas claros e realistas.
    *   Roteiro de acompanhamento para o avaliador.
*   **Preparação do Ambiente:** Configurar o local (laboratório ou campo), software, hardware e ferramentas de captura de dados (câmeras, gravadores, software de registro).
*   **Teste-Piloto:** Realizar um teste completo com uma pessoa não envolvida no projeto para identificar e corrigir problemas no planejamento, nos materiais ou na configuração.
*   **Agendamento:** Agendar data, horário e local com os participantes.

#### **11. Execução e Análise**
A execução da avaliação segue o método escolhido. Para métodos de observação:
*   **Sessão:** Receber o participante, quebrar o gelo, explicar objetivos e procedimentos, obter consentimento.
*   **Coleta de Dados:** Aplicar pré-teste, permitir exploração livre, apresentar cenários de tarefas, observar sem interferir (usando a técnica *think aloud* se apropriado), aplicar pós-teste.
*   **Análise:** Interpretar os dados individuais e depois consolidá-los para encontrar **recorrências** (padrões comuns entre participantes) que indiquem problemas gerais, não apenas particulares.
*   **Relato dos Resultados:** Comunicar os findings de forma clara, incluindo:
    *   Objetivos e métodos utilizados.
    *   Perfil dos participantes.
    *   Sumário dos dados coletados (com tabelas/gráficos).
    *   Interpretação e análise.
    *   **Lista de problemas identificados** priorizados.
    *   Recomendações e um plano para o reprojeto.

A avaliação revela **tendências** e problemas potenciais, não certezas absolutas. Mesmo a ausência de problemas encontrados não garante qualidade perfeita, mas indica que nenhum problema foi detectado dentro do escopo e método daquela avaliação específica.

---
**Conclusão:** O planejamento de avaliação de IHC é uma etapa metódica e essencial para garantir que produtos interativos sejam verdadeiramente úteis, utilizáveis e satisfatórios. Através da aplicação de frameworks como o DECIDE e da escolha criteriosa de métodos, momentos e locais de avaliação, os designers podem obter insights valiosos que guiam a criação de experiências de usuário de alta qualidade.

