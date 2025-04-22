# **Linguagem da Teoria dos Conjuntos**

## 1. Representação de Conjuntos

> *📌 Conjunto: coleção de objetos com uma característica comum.*

### Formas de representação:

- **Explícita**: elementos listados entre chaves → Ex: `A = {1; 3; 5}`
    
- **Implícita**: descreve uma propriedade dos elementos → Ex: `A = {x | x ∈ Z e x² < 9}`

> *⚠️ Evite ambiguidade: use ponto e vírgula para separar elementos numéricos com decimais.*

### Símbolos importantes:

- `∈` → Pertinência
- `⊂` → Inclusão
- `∅` → Conjunto vazio
- `⊄`, `∉` → Não inclusão, não pertinência

### Relações entre Conjuntos

- Inclusão: `A ⊆ B` se todo elemento de A está em B.
- Igualdade: `A = B` se ambos têm os mesmos elementos.
- Conjunto vazio: `∅ ⊆ A`, para qualquer conjunto A.

---
## 2. Intervalos Na Reta Numérica e Valor Absoluto

### Conjuntos Numéricos

- `ℕ` = Naturais
- `ℤ` = Inteiros
- `ℚ` = Racionais
- `ℝ` = Reais

### Intervalos na Reta Real

| **Tipo**              | **Notação** | **Inclui extremos?** |
| --------------------- | ----------- | -------------------- |
| Aberto                | (a; b)      | Não                  |
| Fechado               | [a; b]      | Sim                  |
| Semiaberto à esquerda | (a; b]      | Sim em b             |
| Semiaberto à direita  | [a; b)      | Sim em a             |

### Valor Absoluto (Módulo)

> *📏 Distância de um número até a origem (0)*

- `|x| = x`, se `x ≥ 0`
- `|x| = -x`, se `x < 0`
    

> *🎯 Exemplo:*  
> `|x - 1| = 3 → x = -2 ou x = 4`

---
## 3. Operações Entre Conjuntos
### Operações com Conjuntos (Diagramas de Venn)

| **Operação** | **Símbolo** | **Descrição**                          |
| ------------ | ----------- | -------------------------------------- |
| União        | `A ∪ B`     | Elementos que estão em A ou B          |
| Interseção   | `A ∩ B`     | Elementos que estão em A e B           |
| Diferença    | `A - B`     | Elementos que estão em A, mas não em B |
| Complementar | `A′`        | Elementos de U que não estão em A      |
