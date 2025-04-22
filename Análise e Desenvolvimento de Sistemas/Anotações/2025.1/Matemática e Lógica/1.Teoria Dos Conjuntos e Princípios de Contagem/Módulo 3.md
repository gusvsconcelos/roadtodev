# **Agrupamentos Complementares**

## 1. Agrupamento com Ordem Relevante

### Arranjos Simples:

- Formar grupos onde a **ordem importa** e **sem repetição**
- Fórmula: `A(n, p) = n! / (n - p)!`

### Permutações Simples:

- Ordenar todos os elementos → `P(n) = n!`

### Permutações com Repetição:

- Fórmula: `P = n! / (a! × b! × ...)`, onde `a`, `b`... são repetições

> *🧠 Exemplo: Anagramas de “matemática” com letras repetidas.*

---
## 2. Agrupamento com Ordem Irrelevante

### Combinações Simples:

- Ordem **não importa** e **sem repetição**
- Fórmula: `C(n, p) = n! / [p! × (n - p)!]`

### Combinações com Repetição:

- Pode repetir elementos
- Fórmula: `C(n + p - 1, p)`

> *🍫 Exemplo: Comprar 8 chocolates entre 3 tipos → `C(3 + 8 - 1, 8) = C(10, 8)`*

### Casos Especiais

#### **Permutação Circular**

> *🔄 Disposição em círculo de n objetos: `(n - 1)!`*

#### **Senhas e Placas**

- Com repetição: `n^p`
- Sem repetição: `n × (n - 1) × ...`