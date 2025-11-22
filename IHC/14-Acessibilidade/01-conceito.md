# Acessibilidade em Interação Humano-Computador

## 1. Introdução e Motivação

Kate, viajante cega de 63 anos, realizou viagem independente de navio pela costa australiana enfrentando desafios reais: necessidade de transcrição de materiais para Braille, leitores de tela, aplicativos como BeMyEyes para descrições visuais remotas, e limitações de dispositivos assistivos por custo, tamanho ou conectividade.

Este caso demonstra que acessibilidade é **condição essencial** para autonomia e participação social, não luxo. No Brasil, é obrigatória desde 2004 (Decreto 5.296 e Lei 13.146/2015).

---

## 2. Conceitos Fundamentais

**Acessibilidade** é a possibilidade de alcance, utilização e compreensão de espaços, produtos e serviços **com segurança e autonomia** por qualquer pessoa, incluindo aquelas com deficiência ou mobilidade reduzida.

**Relação com usabilidade**: acessibilidade é condição **indispensável** à usabilidade. Não há eficácia, eficiência ou satisfação se o sistema não é acessível. Remover barreiras significa **incluir mais pessoas**.

**Benefícios universais**: acessibilidade beneficia não apenas pessoas com deficiências permanentes, mas também usuários com limitações temporárias (braço quebrado), situações adversas (luz solar intensa, ambientes ruidosos), idosos com declínio natural de capacidades, e diversos dispositivos/conexões.

---

## 3. Tipos de Deficiências e Barreiras

### **Deficiências Visuais**
Desde baixa visão até cegueira total e daltonismo. Dependem de leitores de tela, displays Braille, amplificação de texto/imagens, personalização de fontes e cores, contraste adequado.

**Barreiras**: imagens sem texto alternativo, vídeos sem audiodescrição, baixo contraste, uso exclusivo de cor para informação.

### **Deficiências Auditivas**
De dificuldade leve até surdez total. Necessitam transcrições, legendas sincronizadas, áudio de alta qualidade, linguagem de sinais, textos simples com imagens.

**Barreiras**: conteúdo só em áudio, ausência de legendas, autoplay sem controle.

### **Deficiências Motoras**
Fraqueza muscular, tremores, falta de coordenação, artrite, amputação, LER, tetraplegia. Usam teclados alternativos, dispositivos apontadores especiais (eyegaze, joysticks), reconhecimento de voz, rastreamento ocular.

**Barreiras**: sites sem suporte completo para teclado, limites de tempo curtos, áreas clicáveis pequenas, navegação inconsistente.

### **Deficiências Cognitivas e Neurológicas**
TDAH, autismo, deficiências intelectuais, ansiedade, depressão, demência, dislexia, disgrafia, discalculia. Necessitam conteúdo estruturado e consistente, rotulagem clara, navegação previsível, supressão de conteúdo piscante, texto simples, conversão texto-fala.

**Barreiras**: layouts complexos, linguagem figurada, instruções vagas, excesso de informação simultânea.

### **Deficiências Relacionadas à Idade**
Idosos experimentam declínio em visão (contraste, cores), audição (sons agudos), destreza física e habilidades cognitivas (memória, concentração). Beneficiam-se das mesmas práticas para deficiências específicas.

---

## 4. Tecnologias Assistivas

Recursos que permitem interação de pessoas com deficiência:

- **Leitores de tela**: convertem texto em fala ou Braille (JAWS, NVDA, Virtual Vision)
- **Displays Braille atualizáveis**: terminais mecânicos dinâmicos
- **Ampliadores de tela**: aumentam e modificam cores
- **Reconhecimento de voz**: comandos verbais
- **Teclados alternativos**: maior espaçamento ou virtuais
- **Dispositivos apontadores alternativos**: rastreamento ocular, controles por pés/mãos/boca
- **Monitores com ajuste para daltonismo**
- **Headmouse**: controle por movimento da cabeça

**NVDA** é leitor de tela livre, aberto e portável para Windows, desenvolvido por programadores cegos, traduzido para 55+ idiomas.

---

## 5. Design Universal vs. Design Inclusivo

### **Design Universal**
Desenvolver produtos e ambientes **utilizáveis por todas as pessoas, na maior extensão possível, sem necessidade de adaptação ou design especializado**. Busca soluções que não discriminem e simplifiquem a vida de todos **sem custo extra**.

**Pressupostos (NBR 15290)**:
- Equiparação nas possibilidades de uso
- Flexibilidade no uso
- Uso simples e intuitivo
- Captação da informação
- Tolerância ao erro
- Dimensão e espaço adequados

**Abrangência**: além da deficiência, considera acesso a hardware/software, conectividade, alfabetização digital, situação econômica, educação, localização geográfica, cultura, idade e linguagem.

**Limitação prática**: quando inviável promover acesso direto, oferecer alternativas via acessórios ou compatibilidade com tecnologias assistivas. É meta ambiciosa relacionada à cidadania.

### **Design Inclusivo**
Usa "inclusivo" reconhecendo que **inclusão é mais alcançável que universalidade** em muitas situações. Substitui "centrado no usuário" por **"sensível ao usuário"**, pois diversidade extrema torna amostragens representativas impossíveis.

**Princípios**:
1. **Reconhecer a exclusão**: identificar quem está sendo excluído e por quê
2. **Aprender com a diversidade**: diversidade é característica humana comum
3. **Resolver para um, estender para muitos**: soluções para deficiências específicas beneficiam todos

**Premissas**:
1. Diferenças nas habilidades são característica comum, não condição especial
2. Se funciona bem para pessoas com deficiência, **funciona melhor para todos**
3. Autoestima e bem-estar dependem de funcionar no ambiente com conforto e independência
4. **Usabilidade e estética são mutuamente compatíveis**

---

## 6. Diretrizes e Normas

### **WCAG 2.2 (Web Content Accessibility Guidelines)**
Organiza-se em **4 princípios (POUR)**:

1. **Perceptível**: conteúdo apresentado de formas perceptíveis
   - Texto alternativo para conteúdo não textual
   - Alternativas sincronizadas para multimídia
   - Conteúdo apresentável de diferentes formas sem perder estrutura
   - Facilitação da distinção entre primeiro plano e fundo

2. **Operável**: componentes de interface e navegação operáveis
   - Funcionalidade acessível via teclado
   - Tempo suficiente para ler e usar conteúdo
   - Evitar conteúdo que pisca mais de 3 vezes/segundo
   - Mecanismos de navegação claros
   - Suporte a múltiplas formas de entrada

3. **Compreensível**: conteúdo e controles compreensíveis
   - Texto legível e compreensível
   - Localização e funcionalidade previsíveis
   - Ajuda para evitar e corrigir erros

4. **Robusto**: compatibilidade com tecnologias assistivas atuais e futuras

**Níveis de conformidade**:
- **Nível A**: mínimo alcançável
- **Nível AA**: intermediário (recomendado para maioria dos sites)
- **Nível AAA**: mais sofisticado (não recomendado como política geral)

### **WAI-ARIA (Accessible Rich Internet Applications)**
Torna aplicações web dinâmicas acessíveis quando HTML puro não consegue. Adiciona atributos HTML que **não modificam aparência ou comportamento**, mas:
- Adicionam/modificam significado de elementos
- Adicionam rótulos/descrições
- Estabelecem relacionamentos entre elementos
- Informam sobre atualizações

**Componentes**:
- **Roles**: tipo de widget (menu, slider, progressbar)
- **States**: estado atual (checked, disabled)
- **Properties**: finalidade ou relacionamento (aria-describedby, aria-label)

**Exemplo**: `<button aria-disabled="true">Salvar</button>`

### **eMAG (Modelo de Acessibilidade em Governo Eletrônico)**
Norteador brasileiro para desenvolvimento de conteúdos digitais do governo federal, em conformidade com WCAG. Ferramentas como **ASES** baseiam-se em eMAG para inspeção automatizada.

---

## 7. Estratégias Práticas

### **Critérios para Enriquecer Acessibilidade**

**1. Condução**: o que será anunciado pelo leitor de tela
- Informar sobre conteúdo disponível e localização relativa
- Indicar valores default e estado de componentes
- Descrever comportamento e instruir sobre atalhos
- Informar sobre extensão da condução

**2. Feedback**: atualização do modelo mental
- Indicar modificações de estado
- Feedback estrutural e de transação

**3. Controle**: dar ao usuário controle sobre condução
- Permitir ativar/desativar e repetir instruções
- Ritmar condução respeitando limites de memória

**4. Coerência**: facilitar reutilização de modelos mentais
- Modos de operação previsíveis e coerentes

**5. Carga de trabalho**: reduzir carga perceptiva e física
- Deslocamento direto ao componente principal
- Instruções seletivas e oportunas
- Condução não repetitiva

### **Dicas por Tipo de Deficiência**

| **Usuário** | **Fazer** | **Não fazer** |
|-------------|-----------|---------------|
| **Autista** | Cores simples, linguagem simples, frases curtas, botões descritivos, layouts consistentes | Cores brilhantes/contrastantes, figuras de linguagem, texto longo, botões vagos, layouts complexos |
| **Baixa visão** | Bom contraste, fonte legível, HTML, cor+forma+texto, layout linear, ampliar 200% | Baixo contraste, informações em downloads, só cor para significado, rolagem horizontal ao ampliar |
| **Deficiência motora** | Ações clicáveis grandes, espaço em formulários, design para teclado/fala/toque, atalhos | Exigir precisão, amontoar interações, muito mouse, timeouts curtos, muita digitação |
| **Surdos** | Linguagem simples, legendas/transcrições, layout linear, dividir conteúdo, suporte variado | Palavras complicadas, só áudio/vídeo, layouts complexos, blocos longos, só telefone |
| **Dislexia** | Imagens apoiando texto, alinhar à esquerda, layout consistente, materiais alternativos, conteúdo curto | Grandes blocos, sublinhar/itálico/MAIÚSCULAS, forçar memorização, muita informação junta |

### **Evitar Elementos Problemáticos**
- Páginas lentas sem indicador de espera
- Pop-ups difíceis de fechar
- Muito texto
- Incerteza sobre links/botões
- **Autoplay**: perigoso, pode causar convulsões—sempre fornecer controle
- Links inativos ou inesperados
- Layout ruim, ícones confusos, FONTES EM MAIÚSCULAS, dark patterns

---

## 8. Processo de Desenvolvimento

Acessibilidade é **usabilidade para pessoas especiais**. Desenvolvimento em três etapas:

### **1. Análise**
- Conhecer perfis: elaborar personas com deficiências
- Conhecer atividades: elaborar cenários de contextos físicos, tecnológicos e organizacionais

### **2. Síntese/Concepção**
- Especificar e conceber interfaces acessíveis
- Envolver representantes de usuários com deficiência
- Modelagem ágil: implementar concepções rapidamente

### **3. Avaliação**
Realizada em paralelo com síntese:

**a) Avaliações por especialistas**: baseadas em contexto de uso e normas (WCAG), realizáveis em qualquer etapa

**b) Inspeções automáticas**: ferramentas percorrem código (ASES, Wave, Axe)
- **Limitação**: identificam ausência de texto alternativo, mas **julgamento humano é imprescindível para avaliar adequação**

**c) Inspeções manuais**: verificar em diferentes navegadores, trocar tamanho de fontes, resoluções, desabilitar cores, navegar só com teclado

**d) Testes com usuários reais**: **Indispensável**. Conformidade com recomendações não garante ser verdadeiramente acessível

---

## 9. Conclusão

**Acessibilidade é lei no Brasil** desde 2004, mas permanece subvalorizada.

**Lições-chave**:

1. **Acessibilidade beneficia todos**: melhorias para cegos ajudam dispositivos móveis; legendas ajudam ambientes ruidosos; navegação por teclado beneficia eficiência

2. **Design Universal é ambicioso mas limitado**; Design Inclusivo reconhece que inclusão (resolver para um, estender para muitos) é meta mais prática

3. **Tecnologias assistivas são essenciais**, mas design deve ser compatível (WAI-ARIA, texto alternativo, navegação por teclado)

4. **WCAG 2.2 e WAI-ARIA são padrões fundamentais**. POUR deve guiar toda decisão de design

5. **Avaliação automatizada é útil mas insuficiente**. Julgamento humano e testes com usuários são insubstituíveis

6. **Processo iterativo e envolvimento de usuários com deficiência** desde análise até avaliação são essenciais

7. **Pequenas escolhas fazem diferença**: contraste, tamanhos ajustáveis, legendas, descrições, navegação previsível, evitar autoplay, tempo suficiente, linguagem simples

O caso de Kate ilustra que acessibilidade é **condição para participação plena na sociedade**. Interfaces inacessíveis excluem milhões e violam princípios legais, éticos e econômicos. Projetar com acessibilidade desde o início é mais eficaz, barato e justo—e **torna produtos melhores para todos**.