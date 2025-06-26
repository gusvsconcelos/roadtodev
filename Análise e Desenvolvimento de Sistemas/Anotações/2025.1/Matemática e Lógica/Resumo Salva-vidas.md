# 1. Teoria dos Conjuntos e Princípios de Contagem

## Conjuntos:

- ==Um **conjunto** é uma coleção de elementos (números, objetos, etc).==
- **Exemplo**: A = {1, 2, 3} → conjunto com 3 elementos.
- **∈** → ==pertence==. Ex: 2 ∈ A
- **⊂** → ==está contido==. Ex: {1, 2} ⊂ A
- Conjunto vazio: ∅ ou {}

## Representações:

- **Explícita**: A = {2, 4, 6}
- **Implícita**: A = {x | x é par e 2 ≤ x ≤ 6}

## Operações com conjuntos:

- **União** (∪): A ∪ B = tudo que está em ==A ou B==
- **Interseção** (∩): A ∩ B = o que está em ==A e B==
- **Diferença** (A - B): o que ==está em A e não está em B==

## Princípios de contagem:

- **Princípio aditivo**: ==se uma tarefa pode ser feita de 2 formas diferentes e excludentes, somamos.==
    
- **Princípio multiplicativo**: ==se uma tarefa pode ser dividida em etapas, multiplicamos as opções de cada etapa.==
    
- **Fatorial (n!)**: ==número de formas de organizar n elementos.== Ex: 3! = 3×2×1 = 6

---
# 2. Gráficos e Interpretação Gráfica

## Intervalos:

- ==São subconjuntos de números reais, representados assim:==
    
    - (a, b): aberto
    - (a, b]: semiaberto
    - [a, b): semiaberto
        
- **Exemplo**: [4, 6] representa os meses abril, maio, junho (usando 1 = janeiro, 2 = fevereiro…)

## Representação:

- Bola cheia = inclui extremidade (colchetes)
- Bola aberta = não inclui (parênteses)

## Plano Cartesiano:

- ==É um gráfico com dois eixos (x e y) para marcar pontos e funções.==

## Pontos notáveis de um gráfico:

- Máximo e mínimo
- Onde cruza o eixo y (f(0))
- Zeros da função (onde f(x) = 0)

---
# 3. Aprofundamento de Funções

## O que é função?

- É uma regra que **liga cada valor de x a um valor de y**.
- Ex: f(x) = 2x + 1

## Termos importantes:

- **Domínio**: valores que posso usar no x
- **Imagem**: os resultados que saem da função (os y)
- **Contradomínio**: todos os valores possíveis para y, mesmo que não sejam atingidos.

## Tipos de funções:

- **Afim** (reta): f(x) = ax + b
- **Quadrática**: f(x) = ax² + bx + c (parábola)
- **Modular**: f(x) = |x| → sempre dá resultado positivo

## Como achar domínio?

- Ver onde a função **existe**:
    
    - Divisão? Não pode dividir por zero.
    - Raiz? Só raiz de número positivo.

---
# 4. Cálculo Proposicional (Lógica)

## Proposição:

- Uma frase que pode ser **verdadeira (V)** ou **falsa (F)**.
    
    - Ex: "2 + 2 = 4" → V

## Conectivos lógicos:

- **¬p**: **negação** (“não p”)
- **p ∧ q**: **conjunção** (“p e q”) → só é V se os dois forem V
- **p ∨ q**: **disjunção** (“p ou q”) → é F só se os dois forem F
- **p → q**: **condicional** (“se p, então q”) → só é F se p for V e q for F
- **p ↔ q**: **bicondicional** (“p se e somente se q”) → só é V se os dois tiverem mesmo valor

## Tabela-verdade:

- Usada para descobrir se uma proposição composta é sempre verdadeira (tautologia), sempre falsa (contradição) ou depende (contingência)

---
# 5. Cálculo de Predicados

## Sentença aberta:

- É uma expressão com variável, como: x > 2
    
    - Só vira proposição (V/F) se a gente disser quem é o x.

## Conjunto verdade:

- É o conjunto de valores de x que tornam a sentença **verdadeira**.
    
    - Ex: x > 2 no conjunto dos naturais N → {3, 4, 5, ...}

## Quantificadores:

- **∀** (universal): “para todo”
    
    - Ex: ∀x ∈ N, x + 1 > x → verdadeiro
        
- **∃** (existencial): “existe”
    
    - Ex: ∃x ∈ N, x² = 4 → verdadeiro

## Negação de quantificadores:

- Negar ∀ vira ∃
- Negar ∃ vira ∀

---
# Resumo da Sobrevivência:

| **Tema**             | **Lembre-se disso**                                          |
| -------------------- | ------------------------------------------------------------ |
| Conjuntos            | ∪, ∩, ∅, ⊂, pertinência (∈)                                  |
| Contagem             | ==Soma = ou, multiplicação = e, fatorial (n!)==              |
| Gráficos             | Intervalos com bola cheia (≥) ou vazia (<)                   |
| Funções              | Domínio e imagem; cuidado com divisão por 0 ou raiz negativa |
| Lógica Proposicional | ∧, ∨, →, ↔, ¬ e tabelas verdade                              |
| Predicados           | Quantificadores (∀, ∃), conjunto verdade                     |
