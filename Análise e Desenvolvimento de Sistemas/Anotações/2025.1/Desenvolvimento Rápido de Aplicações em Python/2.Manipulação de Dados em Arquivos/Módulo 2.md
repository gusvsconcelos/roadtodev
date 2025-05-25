# **Funções de Manipulação de Strings**

## 1. Operações com strings

> *🧹 Limpeza e preparação de texto é rotina em qualquer pipeline de dados.*

**Principais métodos**:

- `strip()`: remove espaços extras e quebras de linha
- `count()`: conta ocorrências de substring
- `split()`: divide string em lista
- `join()`: junta lista de strings em uma única string

### `strip()`

- Remove espaços no início/fim da string
- Ideal pra limpar entrada de usuário e dados de arquivo

### `count()`

- Conta quantas vezes uma substring aparece
- Cuidado: inclui ocorrências dentro de outras palavras

```python
frase = "Eu amo comer amoras"
print(frase.count("amo"))  # Retorna 2
```

> *📌 Use `split()` + `count()` pra maior precisão.*

### `split()`

- Divide a string com base em um delimitador (padrão: espaço)
- Retorna uma lista de partes

```python
"Carro,moto,avião".split(',')  # ['Carro', 'moto', 'avião']
```

### `join()`

- Junta elementos de uma lista com um separador definido
- Ideal pra formatar listas em strings

```python
", ".join(["Python", "Java", "C++"])  # "Python, Java, C++"
```

---
## 2. Formatação de strings

> *🧾 Exibir dados com clareza = UX até no terminal.*

**Formas de formatar**:

- `f"{}"` (f-string): simples e direto
- `.format()`: mais controle
- **Concatenar com** `+`: menos recomendado

### F-Strings (recomendado)

```python
nome = "Python"
print(f"Aprendendo {nome}!")
```

- Suporta expressões, métodos e operações

```python
pi = 3.14159
print(f"{pi:.2f}")        # 3.14
print(f"{pi:7.3f}")       # '  3.142'
```

### Datas com `datetime`

```python
from datetime import datetime
data = datetime.now()
print(f"{data:%d/%m/%Y}")  # 14/04/2025
```

> *✅ Use f-strings em Python 3.6+. Mais limpas, mais legíveis.*

---
## 3. Codificação com Python (ZENIT POLAR)

> *🔐 Substituições simples são didáticas, mas não seguras.*

**Cifra ZENIT POLAR**:
| Z ↔ P | E ↔ O | N ↔ L | I ↔ A | T ↔ R |

- Troca letras das palavras “ZENIT” com as de “POLAR”
- Substituição é bidirecional e case-insensitive

```python
def zenit_polar_replace(text):
    trocas = [('z','p'), ('e','o'), ('n','l'), ('i','a'), ('t','r'),
              ('Z','P'), ('E','O'), ('N','L'), ('I','A'), ('T','R')]
    for old, new in trocas:
        text = text.replace(old, new)
    return text
```

### Exemplo prático:

```python
frase = "The quick brown fox jumps over the lazy dog"
frase = frase.title()  # Capitaliza cada palavra
palavras = frase.split()
codificadas = [zenit_polar_replace(p) for p in palavras]
resultado = " ".join(codificadas)

print("Original:", frase)
print("Coded:", resultado)
```