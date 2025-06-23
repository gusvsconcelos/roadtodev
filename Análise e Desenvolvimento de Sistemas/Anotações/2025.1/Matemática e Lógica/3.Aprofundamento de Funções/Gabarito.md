# Apostila Explicativa - Funções AVS Estácio

A seguir estão os principais conteúdos cobrados na prova AVS com base no arquivo fornecido. Cada questão foi analisada com explicações simples, resoluções passo a passo e dicas de chute para te ajudar a aprender de verdade.

---

## ✅ Questão 1 - Imagem de Função por Partes

**Função:**

f(x)={−x−1,se x≤−1−x2+1,se −1<x<1x−1,se x≥1f(x) = \begin{cases} -x - 1, & \text{se } x \leq -1 \\ -x^2 + 1, & \text{se } -1 < x < 1 \\ x - 1, & \text{se } x \geq 1 \end{cases}

### Objetivo:

Determinar a **imagem** da função — ou seja, os valores que "saem" da f(x).

### Passos:

- Primeiro trecho (x≤−1x \leq -1): f decresce e tende a −∞-\infty, com f(-1) = 0.
    
- Segundo trecho (−1<x<1-1 < x < 1): f(x)=−x2+1f(x) = -x^2 + 1 tem máximo em x = 0, então varia de (0, 1)
    
- Terceiro trecho (x≥1x \geq 1): f(x) = x - 1, com f(1) = 0 e cresce até +∞+\infty
    

### Imagem total:

(0,1)∪[0,+∞[=[0,+∞[(0, 1) \cup [0, +\infty[ = [0, +\infty[

**Gabarito:** [0, +∞[

**Dica de chute:** Funções por partes que envolvem x2x^2 e termos lineares costumam gerar intervalos abertos e semiabertos.

---

## ✅ Questão 2 - Domínio da Função com Raiz e Denominador

**Função:**

f(x)=x2−6x+5x2−43f(x) = \frac{\sqrt{x^2 - 6x + 5}}{\sqrt[3]{x^2 - 4}}

### Passos:

1. Raiz quadrada no numerador: exige x2−6x+5≥0x^2 - 6x + 5 \geq 0
    
    - Raízes: x = 1 e x = 5 → Sinal: (−∞,1]∪[5,+∞)( -\infty, 1 ] \cup [5, +\infty )
        
2. Raiz cúbica: pode ser negativa, mas o denominador **não pode ser 0** → Excluir x = ±2
    

### Domínio final:

(−∞,1)∪(−∞,−2)∪(5,+∞)( -\infty, 1 ) \cup ( -\infty, -2 ) \cup (5, +\infty )

**Gabarito:** R \ { -2, 2 }

**Dica de chute:** Quando tiver raiz quadrada e raiz cúbica juntas, o problema quase sempre é x → 0 ou pontos de exclusão.

---

## ✅ Questão 3 - Propriedades da Função Seno

Função: f(x)=sin⁡(x)f(x) = \sin(x)

### Verdadeiras:

- (1) Paridade: seno é **impar**: sin⁡(−x)=−sin⁡(x)\sin(-x) = -\sin(x) → **falsa**
    
- (2) Período: 2π2\pi, não π\pi → **falsa**
    
- (3) Seno é sobrejetora: sim, pois cobre de -1 a 1 → **verdade**
    
- (4) Os valores dados são corretos
    

**Gabarito correto:** 3 e 4 apenas

**Dica de chute:** Se aparece "par" e a função for seno, provavelmente é **falso**. Cos(x) sim é par.

---

## ✅ Questão 4 - Função Imposto de Renda (por partes)

**Condições:**

- Até R$10.000,00 → Isento
    
- Entre R$10.000 e R$20.000 → 10%
    
- Acima de R$20.000 → 20%
    

**Imagem da função:**

- 0 (isento)
    
- de 10.000 → 1.000 reais
    
- de 20.000 → 4.000 reais
    
- depois disso, valores acima de 4.000
    

**Imagem:** [0, 1.000] \cup (4.000, +\infty[

**Gabarito:** [0, 1000] \cup (4000, +\infty[

**Dica de chute:** Se a função tem saltos (trocas bruscas), a imagem costuma ser unida com união de dois intervalos.

---

## ✅ Questão 5 - Função Crescente e Recursiva

**Dado:** f(2x)=2f(x)f(2x) = 2f(x) e f(4)=8f(4) = 8

### Resolver:

- Se f(4)=8f(4) = 8, então:
    
    - f(2)=4f(2) = 4 (porque f(4)=2f(2)f(4) = 2f(2))
        
    - f(1)=2f(1) = 2
        

**Gabarito:** f(1) = 2

**Dica de chute:** Quando a função tem f(2x) = 2f(x), é comum que f(x) = kx. Tente usar isso para achar o valor.

---

## ✅ Questão 6 - Função Periódica

**Dado:** f(x+4) = f(x) e f(2) = 5

### Como calcular f(6)?

- 6 = 2 + 4 → mesma resposta
    
- f(6) = f(2) = 5
    

**Gabarito:** 5

**Dica de chute:** Se a função é periódica, repita o valor da entrada de acordo com o período.

---

## ✅ Questão 7 - Injetora, Sobrejetora e Bijetora

**Função:** f(x) = 2x + 1

- Linha reta crescente → **injetora** (valores de f(x) diferentes para x diferentes)
    
- Como o contradomínio é R, e f(x) cobre todo R → **sobrejetora**
    
- Injetora + sobrejetora = **bijetora**
    

**Gabarito:** A função é injetora e sobrejetora.

**Dica de chute:** Funções lineares do tipo f(x) = ax + b com a ≠ 0 são sempre bijetoras em R.

---

## ✅ Questão 8 - Domínio de Função Racional

**Função:** f(x) = 1 / (x - 2)

- Não pode dividir por 0 → x ≠ 2
    

**Gabarito:** R \ {2}

**Dica de chute:** Quando tiver x no denominador, sempre exclua os valores que zeram o denominador.

---

## ✅ Questão 9 - Função por partes e inversa

**Função:**

f(x)={3x+3,x≤0x2+4x+3,x>0f(x) = \begin{cases} 3x + 3, & x \leq 0 \\ x^2 + 4x + 3, & x > 0 \end{cases}

### Passos:

- Ambas as partes são injetoras no seu domínio
    
- Função é bijetora
    
- Calcular f(0): 3(0) + 3 = 3 → f(0) = 3 → f^(-1)(3) = 0
    

**Gabarito:** f é bijetora e f^-1(3) = 0

**Dica de chute:** Quando pedem f^(-1)(a), tente achar x tal que f(x) = a. Verifique qual pedaço da função usar.

---

**Fim da apostila. Bons estudos!**  
Se quiser mais questões resolvidas ou simulados desse mesmo estilo, é só pedir!