O **Diagrama de Visão Geral de Interação (Interaction Overview Diagram)** é um tipo de diagrama UML que mostra **como vários diagramas de interação se conectam**, funcionando como um **mapa** que organiza diferentes cenários do sistema (normalmente diagramas de sequência).

Ele serve para **visualizar o fluxo geral** do comportamento, sem entrar nos detalhes de cada interação.

---

## 🔹 1. Para que ele serve

* Mostrar **ordem**, **decisões**, **alternativas**, **loops** e **paralelismo** entre interações.
* Ajudar a entender **fluxos complexos** compostos por vários diagramas de sequência.
* Facilitar a leitura: "primeiro acontece X, depois Y, se falhar vai pra Z".

---

## 🔹 2. Como ele funciona

Ele usa os mesmos elementos de um **Diagrama de Atividades**, mas no lugar das atividades simples, coloca **frames** que representam interações completas.

### Elementos:

* **Nó inicial** ●
* **Nó final** ◎
* **Decisão** ◇ (if/else)
* **Merge** (juntar caminhos)
* **Fork/Join** (paralelismo)
* **Setas** (fluxo)
* **Frames de interação** → representam outro diagrama (sequência ou comunicação)

---

## 🔹 3. Frames (coração do diagrama)

O frame é um **retângulo** que contém algo como:

```
ref sd Login
```

Significa:
👉 “Nesta etapa, execute o Diagrama de Sequência chamado Login”.

Eles substituem ações simples e permitem manter o diagrama principal limpo.

### Por que uns são maiores que outros?

Só questão **visual** para caber o nome ou indicar que aquele trecho agrega mais conteúdo, mas não muda o significado.

### Para que servem

* Organizam cenários completos
* Mantêm rastreabilidade com os diagramas detalhados
* Permitem montar o fluxo geral sem poluir o diagrama

---

## 🔹 4. Como ler o Diagrama de Visão Geral

1. Começa na bolinha inicial.
2. Segue as setas.
3. Cada retângulo (frame) é uma interação detalhada.
4. Quando chega num losango, tem escolha: caminho A ou B.
5. Se tiver fork/join, significa paralelismo.
6. Chega no nó final.

---

## 🔹 5. Relação com Diagramas de Sequência e Comunicação

* O **Visão Geral** mostra **o fluxo entre eles**.
* O **Sequência** mostra **o detalhe de cada interação**.
* O **Comunicação** mostra **quem fala com quem**.
* O Visão Geral **não substitui** esses diagramas — ele **organiza**.

---

## 🔹 6. Quando usar esse diagrama

* Caso de uso complexo com vários caminhos.
* Sistemas com muitos diagramas de sequência.
* Processos que têm vários níveis de decisão.
* Para apresentar visão geral em documentação ou reuniões.

---

## 🔹 7. O que ele NÃO mostra

* Mensagens detalhadas entre objetos.
* Tempos e ordem cronológica interna de cada interação.
* Objetos individualmente (isso fica pros Diagramas de Sequência).

---

## 🔹 8. Em resumo

O **Diagrama de Visão Geral de Interação** é como o **sumário de um livro**:

* Mostra os capítulos (interações).
* Mostra a ordem deles.
* Mostra alternativas e loops.
* Os detalhes estão dentro dos diagramas referenciados.

**Ele é um "mapa de fluxos" composto por outros diagramas.**

---
