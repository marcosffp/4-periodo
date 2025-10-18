# 📘 Resumo Didático: Avaliação Heurística em IHC

## O que é Avaliação Heurística?

A **Avaliação Heurística** é um método de verificação de usabilidade que ajuda a identificar problemas em interfaces (sites, aplicativos, sistemas) **sem a necessidade de testar com usuários reais**.

- É como uma “revisão especializada”: avaliadores experientes examinam a interface e apontam onde ela pode causar confusão ou dificuldade para quem vai usar.
- É um processo **rápido, barato e eficiente**, ideal para ser usado durante o desenvolvimento do sistema.

> 🔍 Imagine que você está revisando a casa de um amigo antes da festa: você verifica se a luz do banheiro funciona, se a mesa está estável, se as taças estão limpas… Tudo para evitar problemas durante a festa. A avaliação heurística faz isso com sistemas.

---

## As 10 Heurísticas de Nielsen

As **heurísticas** são como “regras de ouro” ou “princípios de boa usabilidade”. Jakob Nielsen criou 10 delas, que são usadas como base para a avaliação. Vamos ver cada uma com exemplos do dia a dia:

1. **Visibilidade do estado do sistema**  
   → O sistema deve mostrar claramente o que está acontecendo.  
   *Exemplo: quando você envia um arquivo, aparece uma barra de progresso.*

2. **Correspondência entre o sistema e o mundo real**  
   → Use palavras e conceitos que o usuário já conhece.  
   *Exemplo: uma lixeira no computador tem o ícone de uma lixeira, não um código binário.*

3. **Controle e liberdade do usuário**  
   → O usuário deve poder desfazer ações ou sair de telas sem se sentir preso.  
   *Exemplo: o botão “Cancelar” ao enviar um e-mail.*

4. **Consistência e padronização**  
   → Mantenha a mesma aparência e comportamento em todo o sistema.  
   *Exemplo: se o botão “Salvar” é verde em uma tela, não pode ser vermelho em outra.*

5. **Prevenção de erros**  
   → Melhor que mostrar erro é evitar que ele aconteça.  
   *Exemplo: confirmação antes de excluir um arquivo.*

6. **Reconhecimento em vez de memorização**  
   → Mostre opções visíveis em vez de obrigar o usuário a decorar comandos.  
   *Exemplo: menus com ícones em vez de só texto.*

7. **Flexibilidade e eficiência de uso**  
   → Ofereça atalhos para usuários experientes.  
   *Exemplo: Ctrl+C e Ctrl+V para copiar e colar.*

8. **Design estético e minimalista**  
   → Mostre apenas o que é importante.  
   *Exemplo: tela de busca do Google: só a barra de pesquisa e o botão.*

9. **Ajude os usuários a reconhecer, diagnosticar e recuperar-se de erros**  
   → Mensagens de erro claras e que ajudam a resolver o problema.  
   *Exemplo: “Senha incorreta. Esqueceu sua senha?”*

10. **Ajuda e documentação**  
    → Ofereça ajuda fácil de encontrar e entender.  
    *Exemplo: botão “Ajuda” no canto da tela com passo a passo.*

---

## Como aplicar a Avaliação Heurística na prática?

A avaliação é feita em etapas:

1. **Preparação**:  
   Os avaliadores estudam o sistema, os usuários e o contexto de uso.

2. **Inspeção individual**:  
   Cada avaliador, sozinho, examina a interface e anota problemas que encontrou, indicando qual heurística foi violada.

3. **Consolidação**:  
   Todos os avaliadores se reúnem, revisam os problemas juntos, definem a gravidade de cada um e criam um relatório único com recomendações de melhoria.

> 👥 Nielsen recomenda usar de **3 a 5 avaliadores** para encontrar a maioria dos problemas (cerca de 65% a 75%).

---

## Como classificar a gravidade dos problemas?

Cada problema encontrado recebe uma nota de severidade:

| Gravidade | Significado | O que fazer? |
|-----------|-------------|--------------|
| **Cosmético** | Problema leve, não atrapalha muito | Corrigir se sobrar tempo |
| **Pequeno** | Atrapalha um pouco, mas dá para contornar | Baixa prioridade |
| **Grande** | Atrapalha bastante, prejudica a experiência | Alta prioridade |
| **Catastrófico** | Impede o uso do sistema | Corrigir urgentemente antes de lançar |

---

## Exemplo real de problema encontrado:

**Problema**: Em um site de login, o botão “Cadastre-se” estava mais destacado que o botão “Entrar”.  
**Heurística violada**: Visibilidade do estado do sistema + Prevenção de erros.  
**Gravidade**: Grande.  
**Justificativa**: O usuário pode clicar errado e achar que precisa se cadastrar de novo.  
**Solução**: Destacar mais o botão “Entrar” e afastar os links secundários.

---

## 🧠 Resumo Rápido (em tópicos)

- ✅ **O que é**: Método de inspeção de usabilidade sem usuários.
- ✅ **Para que serve**: Encontrar problemas de interface antes de lançar o sistema.
- ✅ **Baseado em**: 10 heurísticas de Nielsen (regras de usabilidade).
- ✅ **Quem faz**: De 3 a 5 avaliadores especialistas.
- ✅ **Como faz**:
  1. Prepara
  2. Inspeciona (cada um)
  3. Reúne e consolida
- ✅ **Classifica problemas** por gravidade: cosmético, pequeno, grande, catastrófico.
- ✅ **Resultado**: Relatório com problemas e sugestões de melhoria.

---
