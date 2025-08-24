# Engenharia Cognitiva em IHC

## 📌 O que é a Engenharia Cognitiva?

A Engenharia Cognitiva foi proposta por **Donald Norman** em 1986 como uma abordagem que aplica conhecimentos da **ciência cognitiva, psicologia cognitiva e fatores humanos** ao design e construção de sistemas computacionais. Seu objetivo é:

- Entender os princípios fundamentais da ação e do desempenho humano.
- Projetar sistemas que sejam **agradáveis, eficientes e prazerosos** de usar.

---

## 🧩 Modelo de Processamento de Informação Humana (MHP)

O **Modelo do Processador Humano de Informações** (MHP) divide o processamento cognitivo em três subsistemas:

1.  **Processador Perceptivo**: Capta estímulos do mundo externo e os transforma em representações mentais.
2.  **Processador Cognitivo**: Processa informações, toma decisões e acessa a memória.
3.  **Processador Motor**: Executa ações físicas com base nas decisões cognitivas.

### Estágios do Processamento (Modelo Simplificado):
1.  **Entrada ou estímulo**
2.  **Codificação**
3.  **Comparação**
4.  **Seleção da resposta**
5.  **Execução da resposta**
6.  **Saída ou resposta**

---

## ⚖️ Teoria da Ação e os "Golfos" de Norman

Norman propõe que toda interação humana com artefatos envolve a **travessia de dois golfos**:

### 1. Golfo de Execução
- **Dificuldade de agir** sobre o sistema.
- Exemplo: Saber qual botão apertar para aumentar o volume.

### 2. Golfo de Avaliação
- **Dificuldade de interpretar** o estado do sistema.
- Exemplo: Entender se o volume realmente aumentou.

### 🧭 Exemplo Prático: Ajustar uma Torneira
- **Problemas comuns**:
  - **Mapeamento**: Qual controle é da água quente? Qual é da fria?
  - **Controle**: Para misturar água, é preciso girar dois controles ao mesmo tempo.
  - **Avaliação**: Dois bocais dificultam saber a temperatura final.

- **Solução melhor**: Uma única alavanca que controla fluxo (para cima/baixo) e temperatura (para direita/esquerda). O mapeamento é aprendido, mas as variáveis físicas correspondem às intenções do usuário.

---

## 🎨 Exemplo Detalhado: Definir uma Cor no Software

### Objetivo: Mudar a cor de fundo para verde oliva (R=85, G=107, B=47)

#### Passo a passo da "Travessia dos Golfos":

1.  **Estabelecimento do objetivo**: Mudar a cor.
2.  **Formulação da intenção**: Usar RGB (85, 107, 47).
3.  **Especificação das ações**:
    - Abrir menu "Preenchimento > Cor".
    - Digitar valores de R, G e B.
    - Clicar em OK.

4.  **Execução e Percepção**:
    - Ação: Clicar no menu.
    - Percepção: Janela de diálogo abre.
    - Interpretação: Controles RGB estão disponíveis.
    - Avaliação: Estou no caminho certo.

5.  **Preenchimento dos valores**:
    - Ação: Digitar 85 no campo R.
    - Percepção: Cor da pré-visualização muda.
    - Avaliação: Valor aceito, prosseguir.

    *(Repete-se para G e B)*

6.  **Confirmação**:
    - Ação: Clicar em OK.
    - Percepção: Janela fecha, cor do retângulo muda.
    - Interpretação: Cor aplicada é a desejada.
    - Avaliação: **Objetivo alcançado!** ✅

---

## 🧠 Modelos Mentais

### O que são?
- Representações internas que as pessoas constroem sobre como as coisas funcionam.
- São **abstrações** baseadas na experiência, não necessariamente precisas.

### Exemplo Clássico: O Forno e a Pizza
- Instrução: Esquentar a 180°C por 30 minutos.
- **Modelo mental errado**: "Se eu aumentar a temperatura, o forno esquenta mais rápido."
- **Realidade**: Termostatos não funcionam assim. A temperatura define o ponto de parada, não a velocidade de aquecimento.

### Por que modelos mentais errados existem?
- Generalizamos experiências do mundo físico (ex.: bater no controle remoto quando a pilha está fraca).
- No mundo digital: Clicar várias vezes em um ícone que não responde imediatamente.

---

## 🎯 O Papel do Designer na Engenharia Cognitiva

O designer deve **minimizar os golfos de execução e avaliação**. Para isso, trabalha com três modelos:

1.  **Modelo de Design**: Como o designer concebe o sistema.
2.  **Imagem do Sistema**: Como o sistema se apresenta (interface, documentação, respostas).
3.  **Modelo do Usuário**: Como o usuário entende o sistema.

### Objetivo Principal:
**Alinhar o modelo do usuário ao modelo de design** por meio de uma **imagem do sistema** clara e intuitiva.

### Exemplo: Design de Organograma
- **Modelo 1 (Ruim)**: Sistema vê o organograma como "caixas e linhas".
- **Modelo 2 (Bom)**: Sistema entende o organograma como "departamentos, subordinados e cargos".
- O segundo modelo tem um **mapeamento direto com o domínio da tarefa**, facilitando o modelo mental do usuário.

---

## 🛠️ Como Ajudar o Usuário?

- **Instruções claras** e linguagem simples.
- **Tutoriais** e ajuda sensível ao contexto.
- **Metáforas** intuitivas (ex.: lixeira para excluir, pastas para organizar).
- **Feedback** imediato e informativo.

### Exemplo: Controle de Volume
- Uma barra deslizante é mais intuitiva que digitar valores em decibéis.
- O usuário **vê e entende** a relação entre a posição do controle e o volume.

---

## ✅ Conclusão

A Engenharia Cognitiva nos ensina que um bom design não é sobre o que o sistema **pode fazer**, mas sobre o que o usuário **consegue fazer** com ele.

Ao entender como as pessoas **processam informações, formulam metas e avaliam resultados**, podemos criar interfaces que **fecham os golfos** e tornam a interação **natural, eficiente e satisfatória**.

> **Design é realmente uma questão de comunicação, só que não com palavras, mas com o modo como as coisas funcionam.** – Donald Norman
