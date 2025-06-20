# Apostila de Reforço para AVS - Matemática e Lógica

## 1. Sistema com valor absoluto

**Objetivo:** Achar quantas soluções existem.
**Solução:** Resolver por intervalos:

- Quando x < 1x < 1: ∣x−1∣+∣x−3∣=−x+1−x+3=−2x+4|x-1| + |x-3| = -x+1 - x + 3 = -2x + 4
    
- Quando 1 < x < 31 < x < 3: ∣x−1∣+∣x−3∣=x−1+3−x=2|x-1| + |x-3| = x-1 + 3 - x = 2
    
- Quando x > 3x > 3: ∣x−1∣+∣x−3∣=x−1+x−3=2x−4|x-1| + |x-3| = x-1 + x - 3 = 2x - 4

Resolva cada trecho e compare com 4. Encontramos **duas soluções reais**.

**Resposta correta:** C) 2

**Dica de chute:** Essas equações geralmente têm 0, 1 ou 2 soluções reais. Se a equação tem simetria com módulos simples e valor ímpar, chute **2**.

---

**Fórmula:** Combinação com repetição:  
C(n + k − 1, k − 1) C(n + k - 1, k - 1)  

**Onde**:

- n = 7n = 7
- k = 3k = 3 (variáveis x, y, z)

C(7 + 3 − 1, 3 − 1) = C(9, 2) = 36 C(7 + 3 - 1, 3 - 1) = C(9, 2) = 36

**Resposta correta:** C) 36

**Dica de chute:** Em problemas tipo "quantas soluções inteiras não negativas", sempre use combinação com repetição.

---

## 3. Contagem - Sanduíche com 1 de cada ingrediente

Opções:

- Pão: 3
- Recheio: 5
- Queijo: 2
- Molho: 5
- Salada: 4

Multiplica:  
**3 × 5 × 2 × 5 × 4 = 600** 3 \times 5 \times 2 \times 5 \times 4 = 600

**Resposta correta:** E) 600

**Dica de chute:** Quando você precisa escolher 1 de cada categoria, é multiplicação direta.

---

## 4. Subconjuntos da interseção

### Conjuntos:

- A = {1, 3, -1, 4}
- B = {3, -1, 5}

Interseção = {3, -1} → possui 22 elementos → 22=42^2 = 4 subconjuntos.

**Resposta correta:** E) 4

**Dica de chute:** Lembrou que subconjuntos = 2n2^n? Está pronto!

---

## 5. Senhas com 2 números e 2 letras (maiúsculas e minúsculas)

- Letras: 52 possibilidades
- Algarismos: 10
- Posições: 4 (misturadas)
- Forma de organizar os 4 caracteres com 2 iguais: 4!2!2!\frac{4!}{2!2!}

Fórmula final:  
102⋅522⋅4!2!2!=102⋅522⋅610^2 \cdot 52^2 \cdot \frac{4!}{2!2!} = 10^2 \cdot 52^2 \cdot 6

**Resposta correta:** (alternativa que representa isso)

**Dica de chute:** Quando misturam letras e números com restrição, pense em permutações com elementos repetidos.

---

## 6. Retirada de balas sem ver (pior caso)

Balas:

- Leite: 8
- Abacaxi: 7
- Chocolate: 6
- Cereja: 5

Para garantir pelo menos 1 de cada:  
8+7+6+1=22 8 + 7 + 6 + 1 = 22 (pior caso: tirar todas as erradas antes)

**Resposta correta:** D) 22

**Dica de chute:** Some todas menos uma e adicione 1.

---

## 7. Mega Sena com 20 números

Escolher 6 números distintos → Combinação simples:  
C(20,6)C(20, 6)

**Resposta correta:** C6^20

**Dica de chute:** Mega Sena = sempre combinação.

---

## 8. Filas com duas pessoas juntas

8 pessoas, 2 devem ficar juntas:

- Trata o par como 1 bloco: 7!7!
- Dentro do bloco: 2 formas  
    7!×2=5040×2=100807! \times 2 = 5040 \times 2 = 10080

**Resposta correta:** C) 10.080

**Dica de chute:** Se duas pessoas devem ficar juntas, resolve como um bloco + permutação interna.

---

## 9. União de conjuntos

- A = ]1; 3/2[
- B = [-1; 5/3]

A⊂BA \subset B → A é parte de B

**União = intervalo maior:** [ -1; 5/3 ]

**Resposta correta:** A)

**Dica de chute:** A união de dois conjuntos contíguos sempre pega o intervalo que cobre ambos.

---

## 10. Anagramas da palavra SUCESSO

- Letras totais: 7
- Repetições:
    
    - S: 3 vezes
    - U: 1
    - C: 1
    - E: 1
    - O: 1

Fórmula:

7!3!=50406=840\frac{7!}{3!} = \frac{5040}{6} = 840

**Resposta correta:** D) 840

**Dica de chute:** Para palavras com letras repetidas, use n!r1!⋅r2!⋯\frac{n!}{r_1! \cdot r_2! \cdots}