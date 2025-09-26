# Arquitetura de Software: Condutores, Requisitos e Modelagem

## 1. Necessidades do Software vs. Condutores Arquiteturais

Assim como na compra de um carro pensamos em velocidade, espaço, segurança e custo, na arquitetura de software temos necessidades análogas que se traduzem em:

- **Desempenho**: Quantos usuários simultâneos? Tempo máximo de resposta?
- **Escalabilidade**: Crescer para milhares/milhões? Nuvem ou local?
- **Disponibilidade**: Pode ficar indisponível? Precisa de redundância?
- **Segurança**: Proteção de dados, autenticação forte, criptografia?
- **Integração**: APIs, ERPs, bancos legados?
- **Custo**: Limites de orçamento para infra e manutenção.

**Condutores arquiteturais** são as necessidades de negócio MAIS RELEVANTES que influenciam diretamente as decisões da arquitetura. Exemplo:
- Aplicação para milhões → desempenho é condutor.
- Dados sensíveis → segurança é condutor.

## 2. Identificando Riscos e Restrições como Condutores

### Riscos:
- Nem todos impactam a arquitetura; apenas os críticos.
- Ex: risco de não escalar → vira condutor de desempenho.

### Restrições:
- **Tecnológicas**: Uso obrigatório de linguagem/framework.
- **De projeto**: Prazos curtos, equipe limitada.
- **Corporativas**: Políticas de compliance, custos.
- As restrições críticas tornam-se condutores.

## 3. Funil dos Condutores Arquiteturais

- Um requisito é **arquitetural** quando influencia diretamente as decisões de arquitetura.
- **Requisitos funcionais**: O que o sistema faz (ex: registrar pedidos).
- **Requisitos não funcionais**: Como se comporta (ex: tempo < 2s, 99,9% disponibilidade).

### Requisitos NÃO Arquiteturais:
- Não afetam significativamente a arquitetura.
- Ex: "O sistema deve enviar e-mails de confirmação" (funcional, mas não altera a estrutura).
- Ex: "Interface em português e inglês" (importante, mas não direciona decisões arquiteturais).

## 4. Qualidade dos Requisitos: Evitando "Requisitos Tolos"

Problemas comuns:
- **Termos genéricos**: "geralmente", "normalmente".
- **Termos relativos**: "rápido", "amigável", "grande número".
- **Termos furtivos**: "poderia", "deveria", "talvez".

### Princípio SMART para Requisitos "Espertos":
1. **Específico**: Ex: "Interface da tela de cadastro de alunos deve ser amigável".
2. **Mensurável**: Ex: "Usuário novato deve usar a tela de cadastro após 30min de treinamento, com ≤1 erro".
3. **Atingível**: Ex: "Disponibilidade de 99,9%" (não 100%, pois é impossível).
4. **Realizável**: Considerar recursos, tempo, orçamento. Ex: Se não há verba para redundância, não exigir tolerância a falhas.
5. **Rastreável**: Saber origem e validação. Ex: "[Requisito aprovado com usuário Paulo Silva]".

Exemplo de requisito SMART:
- **Ruim**: "O sistema deve ser rápido".
- **Bom**: "A tela de cadastro deve ter tempo <8s e suportar 20 usuários simultâneos das 15h às 19h".

## 5. Quando a Arquitetura Falha (Casos Reais)

Ignorar condutores arquiteturais custa caro depois:
- **Caso 1**: Email não funcionou por restrições de segurança (certificados/HTTPS) não consideradas.
- **Caso 2**: Sistema não compatível com Firefox → refazer toda camada JavaScript.
- **Caso 3**: Tempo médio de caso de uso: 40s em produção.
- **Caso 4**: Deadlocks no banco paralisavam lançamento de notas.

## 6. Formulação Estratégica: Escolha de Tecnologias

### Mecanismos Arquiteturais:
São soluções recorrentes para problemas comuns. Existem em três estados:
1. **Análise**: Estudo de opções (ex: autenticação por senha, 2FA, biometria).
2. **Design**: Decisão técnica (ex: escolher Kerberos por não trafegar senhas em texto).
3. **Implementação**: Tecnologia específica (ex: Active Directory para Kerberos em ambiente Microsoft).

Exemplo de tabela de mecanismos:
| Mecanismo de Análise | Mecanismo de Design   | Mecanismo de Implementação      |
|----------------------|-----------------------|----------------------------------|
| Front-End            | Interface com Usuário | Bootstrap, JavaScript, HTML5, CSS |
| ESB                  | Integração            | MuleESB                          |
| Persistência         | Banco relacional      | Microsoft SQL Server             |

### Processo Iterativo:
1. Identificar requisitos (ex: segurança com padrões abertos).
2. Escolher mecanismos de análise (ex: autenticação).
3. Refinar em design (ex: Kerberos).
4. Implementar com tecnologia (ex: Active Directory).

## 7. Modelagem da Arquitetura

### Para que modelar?
- **Comunicar**: Facilitar entendimento entre times.
- **Validar**: Testar a arquitetura antes de implementar.
- **Documentar**: Criar um "mapa" do sistema.

### Visões da Modelagem (com diagramas):
- **Visão de Caso de Uso**: Diagramas de caso de uso e sequência.
- **Visão Lógica (Projeto)**: Diagramas de classes, estado, interação.
- **Visão de Implementação**: Diagramas de componentes.
- **Visão de Processo**: Diagramas de processos.
- **Visão de Implantação**: Diagramas de implantação (topologia, distribuição).

Exemplo: A visão de implantação mostra como o sistema é distribuído em servidores, balanceadores, etc., afetando desempenho e escalabilidade.

## 8. Conclusão

Definir uma boa arquitetura requer:
- Identificar **condutores arquiteturais** (necessidades, riscos, restrições críticas).
- Escrever requisitos **SMART** (específicos, mensuráveis, etc.).
- Escolher tecnologias através de **mecanismos** (análise → design → implementação).
- **Modelar** para comunicar, validar e documentar.

Ignorar esses passos leva a falhas caras em produção. A arquitetura deve ser baseada em decisões racionais, não em emoções ou modismos!