# **Emprego dos Diagramas de Estado e de Atividades no Projeto de Sistema**

## Transição entre Estados

Os diagramas de estados e atividades são fundamentais para modelar o comportamento de objetos em um sistema de software. ==Um objeto está sempre em um estado específico, e pode mudar de estado em resposta a eventos internos ou externos, resultando em uma transição de estados.==

## Diagrama de Estados

Um diagrama de estados (ou diagrama de máquina de estado) é uma representação gráfica que descreve o ciclo de vida de um objeto, incluindo seus estados, eventos e transições. ==É importante ressaltar que nem todas as classes requerem um diagrama de estados; eles são aplicáveis apenas àquelas que possuem um comportamento dinâmico significativo.==

**Elementos Básicos**:
- **Estados**: Representados por retângulos com bordas arredondadas. Cada estado é definido pelas condições dos atributos do objeto.
- **Estado Inicial**: Indicado por um círculo preenchido; é o ponto de partida do diagrama.
- **Estado Final**: Representado por um círculo parcialmente preenchido, podendo haver múltiplos estados finais.
- **Transições**: Linhas com setas que conectam estados, indicando a mudança de um estado para outro, acompanhadas de eventos e ações.

## Identificação de Elementos

**Para construir um diagrama de estados eficaz:**
1. **Identifique os Estados Relevantes**: Avalie os possíveis valores dos atributos do objeto.
2. **Identifique Eventos e Transições**: Quais eventos disparam transições entre estados?
3. **Condições de Guarda**: Existem fatores que condicionam a transição? Se sim, são modelados como condições de guarda.
4. **Ações e Atividades**: Defina as ações a serem executadas durante as transições.

## Diagrama de Atividades

==Os diagramas de atividades representam estados de uma atividade, focando em fluxos de controle ao invés de estados de objetos.== Eles são frequentemente comparados a fluxogramas, mas incluem notações para ações concorrentes e sua sincronização.

**Elementos de um Diagrama de Atividades**:
- **Fluxo de Controle Sequencial**: Inclui estados de ação, transições de término, pontos de ramificação e de união.
- **Fluxo de Controle Paralelo**: Permite a execução simultânea de atividades, ==utilizando barras de bifurcação (fork) e junção (join) para gerenciar a sincronização.==

**Raias de Natação**: Em processos de negócios, diferentes agentes podem realizar atividades paralelamente. ==Raias de natação dividem o diagrama em compartimentos que representam as responsabilidades de cada agente.==