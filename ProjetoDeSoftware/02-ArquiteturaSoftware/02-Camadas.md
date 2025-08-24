### Arquitetura em Camadas

A **Arquitetura em Camadas** é um dos padrões de design de software mais fundamentais e amplamente utilizados, especialmente em sistemas de grande porte. Ela organiza o sistema em grupos de funcionalidades relacionadas, chamadas de **camadas**, que são dispostas de forma hierárquica, como as camadas de um bolo 🎂.

---

#### 🧠 **Conceito Central**

- **Organização Hierárquica**: As camadas são empilhadas umas sobre as outras, e cada uma tem uma responsabilidade específica.
- **Regra de Dependência**: Uma camada só pode usar serviços (métodos, classes, exceções, etc.) da camada **imediatamente inferior**. Isso impõe disciplina e reduz o acoplamento entre as partes do sistema.

---

#### 🌐 **Exemplo Clássico: Protocolos de Rede (TCP/IP)**

A arquitetura em camadas é amplamente utilizada em redes de computadores. O modelo TCP/IP é um exemplo perfeito:

| Camada               | Exemplos de Protocolos                                  | Função                                                                 |
|----------------------|---------------------------------------------------------|------------------------------------------------------------------------|
| **Aplicação**        | HTTP, FTP, SMTP, SSH, DNS                               | Interage diretamente com o usuário ou aplicativo.                      |
| **Transporte**       | TCP, UDP                                                | Garante a entrega dos dados (confiável ou não).                        |
| **Internet (Rede)**  | IP, ARP, ICMP                                           | Endereçamento e roteamento de pacotes entre redes.                     |
| **Enlace de Dados**  | Ethernet                                                | Controla o fluxo de dados em uma rede local (ex.: rede Wi-Fi ou cabo). |
| **Física**           | Cabos, ondas de rádio, sinais elétricos                 | Transmissão física dos bits pela rede.                                 |

**Como funciona na prática:**
- O **HTTP** (camada de aplicação) pede para o **TCP** (camada de transporte) enviar seus dados.
- O **TCP** por sua vez, usa os serviços do **IP** (camada de internet).
- O **IP** se apoia em um protocolo de enlace, como o **Ethernet**.
- Por fim, o **Ethernet** usa a infraestrutura física (cabos, roteadores) para transmitir os dados.

---

#### ✅ **Vantagens da Arquitetura em Camadas**

1.  **Redução da Complexidade**: Divide um sistema complexo em partes menores e gerenciáveis.
2.  **Manutenção e Evolução Facilitadas**: Isolar funcionalidades em camadas torna mais fácil encontrar e corrigir bugs, além de adicionar novas features.
3.  **Substituição e Reutilização**:
    - É fácil **trocar uma camada** sem afetar as outras. Por exemplo, trocar TCP por UDP na camada de transporte, se a aplicação permitir.
    - Uma **camada inferior pode ser reutilizada** por várias superiores. O protocolo TCP, por exemplo, é usado por HTTP, SMTP, FTP, etc.
4.  **Disciplina de Dependências**: A regra rígida de comunicação (só com a camada inferior) evita que o sistema vire uma "bagunça" de dependências, tornando-o mais robusto e compreensível.

**Curiosidade Histórica:** Esse padrão foi proposto pioneiramente por **Edsger W. Dijkstra** em 1968 para o sistema operacional THE. Ele definiu camadas para multiprogramação, memória, comunicação entre processos, E/S e programas de usuário, destacando que os benefícios são ainda maiores em projetos de grande escala.

---

#### 🏗️ **Variações Práticas no Desenvolvimento de Software**

Na construção de sistemas de informação, duas variações são muito comuns:

##### 1. Arquitetura em Três Camadas (3-Tier)

É o padrão mais comum para aplicações web e corporativas. Cada camada pode até ser executada em um servidor diferente, caracterizando um sistema **distribuído**.

| Camada                 | Também Conhecida como | Função                                                                                              | Exemplo no Sistema Acadêmico                                                                                                |
|------------------------|------------------------|-----------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------|
| **1. Apresentação**    | Interface do Usuário   | Toda a interação com o usuário. Exibe informações, coleta dados, trata eventos (cliques, formulários). | Um formulário web onde o professor vê a lista de alunos e digita as notas.                                                  |
| **2. Lógica de Negócio** | Aplicação              | O "cérebro" do sistema. Implementa as regras de negócio, processa dados e coordena as operações.      | Valida se a nota digitada está entre 0 e 10 (regra de negócio). Coordena o salvamento após a validação.                     |
| **3. Dados**           | Persistência           | Armazena e recupera os dados do sistema, geralmente em um banco de dados.                            | Uma tabela no banco de dados chamada "Notas" onde as notas validadas são salvas.                                            |

**Detalhes Importantes:**
- A camada de Lógica de Negócio pode ser subdividida em módulos como:
    - **Fachada (/Facade)**: Fornece uma interface simples e unificada para a camada de apresentação usar, escondendo a complexidade interna.
    - **Módulo de Persistência**: Isola o código de acesso ao banco de dados (ex.: operações de INSERT, SELECT), tornando a troca do banco de dados mais fácil.

##### 2. Arquitetura em Duas Camadas (2-Tier)

É uma versão mais simples e antiga, também conhecida como modelo **cliente-servidor "gordo"** (fat client).

- **O que é:** As camadas de **Apresentação** e **Lógica de Negócio** são unidas em uma única camada que roda na máquina do cliente.
- A única camada remota/separada é o **Banco de Dados**.
- **Desvantagem:** Todo o processamento da lógica de negócio acontece no computador do usuário final. Isso exige que as máquinas clientes tenham **bom poder computacional** e torna a manutenção e atualização da lógica mais difícil (é preciso atualizar o software em todas as máquinas clientes).

---

### 🧩 **Conclusão**

A **Arquitetura em Camadas** é a base para a construção de sistemas software organizados, escaláveis e de fácil manutenção. Ao dominar esse conceito, você compreende a fundo como grandes aplicações e protocolos que usamos diariamente (como a internet) são estruturados.

- Use **Três Camadas** para a maioria dos sistemas web e corporativos modernos, pois ela oferece melhor separação de concerns, segurança e escalabilidade.
- Entenda que a **Duas Camadas** é uma opção mais simples, mas com limitações significativas para sistemas complexos.

