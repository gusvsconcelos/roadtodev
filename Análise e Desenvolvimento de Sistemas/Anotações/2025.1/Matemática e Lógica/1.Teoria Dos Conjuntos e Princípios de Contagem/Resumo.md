## TEORIA DOS CONJUNTOS E PRINCÍPIOS DE CONTAGEM

---
### TEORIA DOS CONJUNTOS

#### Conceito:

- ==Um **conjunto** é uma coleção de elementos distintos e bem definidos.==
- **Exemplo**: o conjunto das vogais é A = {a, e, i, o, u}.

#### Representação:

- **Por extenso**: B = {1, 2, 3, 4}
- **Por propriedade**: B = {x ∈ N | x ≤ 4}
- **Diagrama de Venn**: usado para representar visualmente os conjuntos e suas relações

#### Relações e símbolos importantes:

- **x ∈ A**: x pertence ao conjunto A
- **x ∉ A**: x não pertence ao conjunto A
- **A ⊆ B**: A está contido em B
- **A ⊂ B**: A é subconjunto próprio de B (A ⊆ B e A ≠ B)
- **A = B**: conjuntos com exatamente os mesmos elementos
- **A ⊈ B**: A não está contido em B

#### Conjunto Universo e Conjunto Vazio:

- **Universo (U)**: ==conjunto de todos os elementos possíveis em um contexto==
- **Vazio (∅)**: ==conjunto sem elementos==

#### Intervalos reais:

- Representação de partes dos números reais
- Tipos:
    
    - **Abertos**: (a, b) = todos os x tais que a < x < b
    - **Fechados**: [a, b] = todos os x tais que a ≤ x ≤ b
    - **Misto**: [a, b), (a, b], etc.
    - **Infinitos**: (-∞, a), [a, +∞), etc.

#### Operações com conjuntos:

1. **União (A ∪ B)**: elementos que pertencem a A ou a B ou a ambos
2. **Interseção (A ∩ B)**: elementos que pertencem aos dois conjuntos
3. **Diferença (A - B)**: elementos que estão em A e não estão em B
4. **Complementar (A')**: elementos que estão no conjunto universo e não estão em A

#### Propriedades:

- **Comutativa**: A ∪ B = B ∪ A, A ∩ B = B ∩ A
- **Associativa**: (A ∪ B) ∪ C = A ∪ (B ∪ C)
- **Distributiva**: A ∩ (B ∪ C) = (A ∩ B) ∪ (A ∩ C)

#### Conjuntos numéricos:

- **N** (naturais): {0, 1, 2, 3, ...}
- **Z** (inteiros): {..., -3, -2, -1, 0, 1, 2, ...}
- **Q** (racionais): números que podem ser escritos em forma de fração
- **R** (reais): todos os anteriores + irracionais como √2, π

---
### PRINCÍPIOS DE CONTAGEM

#### =️ Princípio da Adição:

- Quando são duas ou mais opções **exclusivas**, o total é a **soma**.
- **Exemplo**: 3 tipos de camiseta + 2 tipos de boné → 5 escolhas diferentes (não combinadas).

#### × Princípio da Multiplicação:

- Quando temos **várias etapas sucessivas**, usamos a **multiplicação**.
- **Exemplo**: escolher camisa (3 opções) e calça (2 opções) → 3 × 2 = 6 combinações.

#### Princípio da Casa dos Pombos (Pigeonhole Principle):

- Se colocarmos mais objetos do que recipientes, pelo menos um recipiente terá mais de um objeto.
- **Exemplo**: 13 pares de meias em 12 gavetas → pelo menos uma tem 2 pares.
    
---

### AGRUPAMENTOS COMBINATÓRIOS

#### Fatorial:

- n! = n × (n-1) × (n-2) × ... × 1
- 4! = 4 × 3 × 2 × 1 = 24
- 0! = 1 (por definição)

#### Permutações:

- **Ordem importa**, n elementos diferentes:
    
    - ==P(n) = n!==
		
- **Permutação com repetição**:
    
    - P(n; a, b, ...) = ==n! / (a! × b! × ...)==
    - ==**Exemplo**: SALAS (5 letras, com A = 2 e S = 2): 5! / (2! × 2!) = 120 / 4 = 30==
        
- **Permutação circular**:
    
    - P(n circular) = ==(n - 1)!==

#### Arranjos:

- Seleciona **p** elementos de um total de **n**, **ordem importa**.
- **Sem repetição**: ==A(n, p) = n! / (n - p)!==
- **Com repetição**: ==A(n, p) = n^p==
- **Exemplo**: placas com 3 letras (26 letras): 26^3 = 17.576

#### Combinações:

- Seleciona **p** elementos de um total de **n**, **ordem não importa**.
- ==C(n, p) = n! / [p! × (n - p)!]==
- **Exemplo**: escolher 3 alunos entre 8 para uma comissão: C(8,3) = 56
    

#### Combinação com repetição:

- ==C(n + p - 1, p)==
- **Exemplo**: comprar 3 frutas dentre 5 tipos (com repetição): C(5 + 3 - 1, 3) = C(7,3) = 35