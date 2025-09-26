# 📘 Resumo: Métodos de Avaliação de Usabilidade

## 1. Introdução aos Testes de Usabilidade Móveis

Os testes de usabilidade não precisam ser feitos apenas em laboratórios caros. Hoje em dia, é possível montar um **laboratório portátil** com:

- **Câmeras de vídeo**
- **Laptops**
- **Rastreadores oculares** (como óculos com eye tracking)
- **Sensores de reconhecimento facial** (para medir emoções)

Esses equipamentos cabem em uma mala ou caixa (lab-in-a-box) e podem ser levados até o usuário, tornando o teste **menos artificial** e **mais natural**.

---

## 2. Rastreamento Ocular (Eye Tracking)

### O que é?
Técnica que monitora para onde uma pessoa olha na tela (ou no ambiente), por quanto tempo e em que ordem.

### Como funciona?
Usa luz infravermelha refletida na córnea do olho e câmeras de alta resolução para capturar o movimento dos olhos.

### O que podemos descobrir?
- **Fixações**: onde a pessoa parou o olhar (100–600 ms)
- **Sacadas**: movimento entre uma fixação e outra
- **Ordem de visualização**: o que chama atenção primeiro
- **Cegueira a banners**: se o usuário ignora anúncios intencionalmente

### Visualizações comuns:
- **Mapa de calor (heatmap)**: cores mostram onde mais se olhou (vermelho = muito, verde = pouco)
- **Gaze plot**: mostra a sequência e duração dos olhares

### Vantagens:
- Revela o que os usuários **realmente veem** (e não só o que dizem)
- Identifica elementos ignorados ou supervalorizados
- Ajuda a validar a hierarquia visual do design

### Limitações:
- Requer **calibração** constante
- Participantes não podem se mover muito
- Equipamentos como óculos, chapéus ou mãos no rosto podem atrapalhar
- **Caro** e exige **muitos participantes** para mapas de calor (cerca de 39)
- Para análise qualitativa, 6 usuários podem ser suficientes

### Exemplo prático:
Em um shopping de Londres, participantes usaram óculos de eye tracking enquanto faziam compras. Descobriu-se que telas de plasma grandes atraíam mais atenção do que se imaginava.

---

## 3. Testes Remotos de Usabilidade

### O que são?
Testes realizados com participantes em seu próprio ambiente, usando ferramentas como Zoom, Teams ou softwares especializados.

### Tipos:
- **Síncronos**: moderador e participante interagem em tempo real
- **Assíncronos**: participante realiza tarefas sozinho; dados são coletados automaticamente

### Vantagens:
- Participantes em diferentes locais geográficos
- Mais barato e prático
- Ideal para pessoas com deficiência
- Dados automáticos de cliques, tempo, etc.

### Desvantagens:
- Risco de falha técnica
- Menos controle do ambiente
- Moderador não está presente para intervir

### Testes Remotos com Moderação:
Combinam vantagens dos presenciais e remotos. O moderador pode:
- Adaptar tarefas durante o teste
- Fazer perguntas complementares
- Garantir que o participante não se distraia

---

## 4. Estudos In-the-Wild (No Mundo Real)

### O que são?
Estudos de campo com **pouco ou nenhum controle** sobre o ambiente ou comportamento do usuário. Ideais para:

- Tecnologias móveis
- IoT (Internet das Coisas)
- Dispositivos domésticos ou públicos

### Como são feitos?
- Observação natural
- Diários (eletrônicos ou em papel)
- Gravações de áudio e vídeo
- Questionários e entrevistas

### Vantagens:
- Comportamento mais **natural e espontâneo**
- Permite testar em contextos reais
- Longa duração (dias, meses ou anos)

### Desvantagens:
- Dificuldade de controlar variáveis
- Interrupções constantes (ex.: chamadas, clima)
- Desafios éticos e de privacidade

### Exemplo:
Pacientes usaram um dispositivo chamado **Painpad** para registrar níveis de dor a cada duas horas, durante internação hospitalar. O estudo mostrou que os pacientes registraram mais dados com o dispositivo do que com os enfermeiros, e a usabilidade foi bem avaliada.

---

## 5. Impacto na Experiência do Usuário

Todos esses métodos ajudam a:

- Identificar problemas de usabilidade **antes do lançamento**
- Validar se o design está **comunicando corretamente**
- Entender o **comportamento real** do usuário
- Coletar dados **em contexto**, não apenas em laboratório
- Melhorar a **acessibilidade** e inclusão

---

## ✅ Conclusão

Os métodos de teste de usabilidade evoluíram muito. Hoje, podemos usar desde **eye tracking** avançado até testes **remotos** e **in-the-wild** para entender melhor como as pessoas interagem com produtos digitais e físicos.

Cada método tem seu lugar:

- **Eye tracking**: para detalhes visuais e atenção
- **Testes remotos**: para alcance e praticidade
- **In-the-wild**: para contextos reais e comportamentos naturais

Escolher o método certo depende dos **objetivos do teste**, do **orçamento** e do **contexto de uso** do produto.

---
