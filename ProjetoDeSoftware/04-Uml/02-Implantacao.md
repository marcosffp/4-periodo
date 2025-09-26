# Resumo: Diagrama de Implantação

Este documento apresenta um resumo detalhado sobre o Diagrama de Implantação, um dos tipos de diagramas estruturais da UML (Unified Modeling Language). O objetivo é fornecer uma compreensão clara e didática sobre sua finalidade, elementos e aplicação, complementando o conteúdo dos slides e facilitando o entendimento para aqueles que não compreenderam o material original.

## 1. Introdução aos Diagramas UML

Os Diagramas UML são divididos em duas categorias principais: Estruturais e Comportamentais. Os diagramas estruturais focam na visão estática do sistema, mostrando o que existe (ex: Classe, Objeto, Pacotes, Componentes, Implantação). Já os diagramas comportamentais focam na visão dinâmica, mostrando como as coisas acontecem (ex: Casos de Uso, Sequência, Atividade, Comunicação, Estados).

O Diagrama de Implantação se encaixa na categoria dos diagramas estruturais e é fundamental para visualizar a arquitetura física de um sistema. Ele representa os dispositivos de hardware, os ambientes de execução e os softwares/artefatos implantados, complementando outros diagramas como os de componentes e casos de uso.

## 2. Onde o Diagrama de Implantação se Encaixa

Este diagrama é essencial para ilustrar a arquitetura física de um sistema, mostrando onde os componentes de software são executados. Ele detalha a infraestrutura necessária para suportar o sistema, incluindo servidores, bancos de dados, dispositivos de cliente (PCs, smartphones) e a forma como eles se conectam. Por exemplo, em um sistema de e-commerce, o diagrama de implantação mostraria onde a interface web, o módulo de pagamento, o módulo de carrinho e o banco de dados estão hospedados e como se comunicam.

É importante notar a complementaridade entre o Diagrama de Componentes e o Diagrama de Implantação. Enquanto o Diagrama de Componentes descreve "o que o sistema tem" (visão de software lógico), o Diagrama de Implantação descreve "onde o sistema roda" (visão de arquitetura física). Juntos, eles permitem ligar o software ao hardware, facilitando a comunicação entre as equipes de desenvolvimento e infraestrutura.

## 3. Elementos do Diagrama de Implantação

Os principais elementos de um Diagrama de Implantação são os **nós** e suas **conexões**.

### 3.1. Nós

Um nó é uma unidade física que representa um recurso computacional na arquitetura do sistema. Geralmente, possui memória, capacidade de processamento ou armazenamento. Pode ser um dispositivo físico (como um servidor, PC, smartphone) ou um ambiente de execução (como uma máquina virtual na nuvem).

**Representação:** Os nós são representados por um cubo. O nome e o tipo do nó são definidos no interior do cubo, sublinhados e separados por dois pontos (ex: `Nome: Tipo`). Essas informações são opcionais, mas úteis para clareza. É possível adicionar outras informações importantes, como fornecedor, sistema operacional ou localização, embora não haja um rótulo padrão para isso.

**Exemplos de Nós:**
*   Servidor de Aplicação (processa requisições do sistema)
*   Servidor de Banco de Dados (armazenamento de dados)
*   Smartphone ou PC Cliente (onde o usuário acessa o sistema)
*   Máquina Virtual na Nuvem (ambiente de execução remoto)

Em arquiteturas cliente-servidor, a camada de apresentação é alocada na máquina do usuário, enquanto o servidor (camadas lógicas inferiores) é executado em outra máquina com maior capacidade de processamento, atendendo a diversos clientes simultaneamente.

### 3.2. Conexões

As conexões ligam os nós e mostram os mecanismos de comunicação entre eles. Elas podem representar meios físicos (cabo, fibra ótica) ou protocolos de comunicação (TCP/IP, HTTP, JDBC, ODBC).

**Representação:** As conexões são representadas por uma linha entre os nós. A conexão pode ser estereotipada para indicar o tipo de comunicação. Por exemplo, computadores pessoais podem se comunicar via HTTP com um servidor de aplicação, e a aplicação no servidor pode se comunicar com um SGBD via ODBC.

## 4. Considerações Adicionais

*   **Rótulos:** Pode-se adicionar rótulos para sistemas operacionais, fornecedores e outras informações relevantes aos nós.
*   **Múltiplos Nós:** Em casos onde vários nós físicos executam a mesma tarefa lógica, isso pode ser representado por múltiplos cubos ou indicando a quantidade diretamente no nó (sem rótulo padrão).

## 5. Comentários Finais

Os diagramas de implantação, apesar de sua simplicidade aparente, são ferramentas muito úteis para mostrar o que é instalado e onde. Eles são particularmente valiosos em instalações mais complexas, garantindo que todos os envolvidos (desenvolvedores, equipe de infraestrutura) tenham uma compreensão clara da arquitetura física do sistema.

## 6. Dicas para Organização do Sistema (Pacotes e Componentes)

Embora não sejam diretamente parte do diagrama de implantação, as dicas sobre pacotes e componentes são relevantes para a organização do software que será implantado:

*   **Pacotes:** Agrupam elementos relacionados para organizar e modularizar o sistema. Devem ter forte coesão, baixo acoplamento entre si, nomes claros e descritivos, e refletir camadas da arquitetura.
*   **Componentes:** Representam módulos de software independentes e reutilizáveis. Cada componente deve ter uma responsabilidade clara, interfaces bem definidas e ser fracamente acoplado. No diagrama de implantação, os componentes serão implantados em nós físicos.

## 7. Exercícios (Exemplos de Aplicação)

O documento apresenta exercícios práticos para a criação de diagramas de componentes e implantação, reforçando a aplicação dos conceitos:

*   **Exercício 1 (Diagrama de Componentes):** Desenvolver um diagrama de componentes para um sistema de gestão acadêmica baseado em microsserviços, onde cada serviço (Alunos, Professores, Cursos, Matrículas, Biblioteca, Financeiro) está em um servidor dedicado com seu próprio SGBD, comunicando-se via um servidor de API e um servidor Web.
*   **Exercício 2 (Diagrama de Implantação):** Desenvolver um diagrama de implantação para um sistema de gestão de biblioteca universitária, detalhando a comunicação entre um Servidor de Aplicação (com módulos de Empréstimos, Devoluções, Catálogo), um Servidor de Banco de Dados (com SGBD e Persistência), computadores pessoais (browser) e um terminal de autoatendimento. As comunicações utilizam protocolos como HTTP e JDBC.

Este resumo visa esclarecer os pontos chave do Diagrama de Implantação, fornecendo uma base sólida para a compreensão da arquitetura física de sistemas de software.

