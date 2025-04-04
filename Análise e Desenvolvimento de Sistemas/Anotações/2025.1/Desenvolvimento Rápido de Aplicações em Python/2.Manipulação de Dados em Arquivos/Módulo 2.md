# **Funções de manipulação de strings**

## 1. Manipulação de strings

Operações como remoção de espaços, conversão entre maiúsculas e minúsculas e substituição de caracteres são ferramentas essenciais para preparar e processar dados de forma eficiente e precisa.

- Método **strip**
- Método **count**
- Método **split**
- Método **join**

### Método *strip*

`strip()` remove espaços extras e caracteres de fim de linha no início e final de uma string. ==É útil, por exemplo, para limpar dados ao processar linhas de um arquivo.==  

**Uso prático do `strip()`:** linhas lidas frequentemente possuem espaços extras ou quebras de linha indesejadas. ==O método `strip()` ajuda a "limpar" essas linhas antes de armazená-las ou processá-las.==

### Método *count*

O método `count()` é usado para contar o número de vezes que uma palavra ou trecho específico aparece em uma string.

- É prático, mas pode apresentar resultados inesperados ao contar substrings que estão dentro de outras palavras.

**Frase**: `"Eu amo comer amoras no café da manhã"`

- Contando `"amo"` com `count()`, o retorno será **2**, pois `"amo"` está em **"amo"** e **"amoras"**.

**Solução para maior precisão:** É possível usar o método `split()`, quebrando a frase em palavras e verificando cada uma individualmente.

### Método *split*

O método `split()` divide uma string em uma lista de partes menores com base em um delimitador (ou separador).  

- **Sem delimitador:** usa espaço como separador padrão.
- **Com delimitador:** ignora o separador na lista resultante.

**Frase**: `"Carro,moto,avião"`

- Resultado de `split(',')`: `["Carro", "moto", "avião"]`

#### *Comparação count vs. split na contagem de palavras*

Ao contar palavras específicas, o método `split()`, combinado com uma comparação, pode ser mais preciso.

**Frase**: `"Eu amo comer amoras no café da manhã"`

- **Usando *count***: Retorna **2** (`"amo"` e `"amoras"`)
- **Usando *split***:
	1. Quebra a frase em palavras (`["Eu", "amo", "comer", "amoras", ...]`)
	2. Itera sobre cada palavra e compara com `"amo"`.
	3. Retorna **1** (somente `"amo"` é contado).

**Resolução Alternativa com Python:** Uma abordagem eficiente para contar palavras em frases pode combinar `split()` e `count()`.

```python
frase = "Eu amo comer amoras no café da manhã"
lista_palavras = frase.split()  # Divide em palavras
contador = lista_palavras.count("amo")  # Conta "amo" na lista
print(contador)  # Retorna 1
```

### Método *join*

O método `join()` é utilizado para concatenar os elementos de um iterável (como uma lista ou tupla) em uma única string, usando um conector definido pelo usuário.

- Esse conector pode ser qualquer string, como uma vírgula `(', ')` ou uma quebra de linha `('\n')`.

```python
conector.join(iteravel)
```

Esta ferramenta é muito útil para organizar dados e transformar listas em strings formatadas de maneira eficiente.

---
## 2. Formatação de Strings

A formatação de strings em Python é essencial para personalizar e apresentar dados de forma clara e profissional. Ela permite incluir variáveis em mensagens, ajustar formatos numéricos e exibir datas adequadamente.

Existem três formas principais de formatar strings:

- **F-strings**: Simplificam a inclusão de expressões e variáveis.
- **Método `format()`**: Oferece maior controle sobre o conteúdo formatado.
- **Formatação manual**: Usa operadores como `'+'` para concatenar strings e variáveis.

### F-Strings

Introduzidas no Python 3.6, as f-strings facilitam a formatação de strings usando a sintaxe `f"Texto {expressao}"`. O conteúdo dentro das chaves `{}` é avaliado e inserido na string.

#### *Exemplos:*

- Inclusão de variáveis:
    
    ```python
    nome = "Python"
    print(f"Aprendendo {nome}!")
    ```
    
- Chamadas de métodos:
    
    ```python
    print(f"{nome.upper()} é incrível!")
    ```
    
- Operações matemáticas:
    
    ```python
    print(f"A soma de 2 + 3 é {2 + 3}.")
    ```
    
- Avaliações booleanas:
    
    ```python
    print(f"2 > 1 é {2 > 1}.")
    ```

### Funcionalidades Avançadas

- **Definição de largura**: Ajusta o número de espaços ocupados por um valor.
    
    ```python
    fruta = "Maçã"
    print(f"{fruta:10}")  # Ocupa 10 espaços.
    ```
    
- **Formatação de números decimais**: Define o número de casas decimais e a largura total.
    
    ```python
    pi = 3.14159
    print(f"{pi:.2f}")  # 2 casas decimais.
    print(f"{pi:7.3f}")  # Total de 7 espaços com 3 decimais.
    ```
    
- **Formatação de datas**: Personaliza a exibição de datas.
    
    ```python
    from datetime import datetime
    data = datetime.now()
    print(f"{data:%d/%m/%Y}")  # Exibe no formato dia/mês/ano.
    ```

### Boas Práticas

- Use f-strings para clareza e simplicidade.
- Para datas, explore o módulo `datetime` para opções avançadas de formatação.
- ==Prefira f-strings em Python 3.6 ou superior para substituir métodos mais trabalhosos.==

---
## 3. Codificando mensagens com Python

A transformação e codificação de strings são habilidades essenciais para manipulação de dados e segurança. Estas práticas ajudam na integração de sistemas, proteção de informações sensíveis e internacionalização de softwares.

### Codificação ZENIT POLAR

A cifra ZENIT POLAR é uma substituição bidirecional e simétrica, onde letras de "ZENIT" são substituídas pelas correspondentes de "POLAR" e vice-versa:

- **Z** <> **P**
- **E** <> **O**
- **N** <> **L**
- **I** <> **A**
- **T** <> **R**

Letras fora dessas palavras permanecem inalteradas.

>*Apesar de simples e educacional, a cifra não é adequada para segurança robusta.*

```Python
def zenit_polar_replace(text):
    # Aplicar a codificação ZENIT POLAR utilizando o método replace
    replacements = [('z', 'p'), ('e', 'o'), ('n', 'l'), ('i', 'a'), ('t', 'r'),
                    ('Z', 'P'), ('E', 'O'), ('N', 'L'), ('I', 'A'), ('T', 'R')]

    for old, new in replacements:
        text = text.replace(old, new)
				
    return text

def main():
    # Entrada da frase e aplicação da codificação
    phrase = "The quick brown fox jumps over the lazy dog"

    phrase = phrase.title()  # Primeira letra de cada palavra em maiúscula

    # Dividir a frase em palavras
    words = phrase.split()

    # Processar cada palavra na lista usando ZENIT POLAR
    coded_words = [zenit_polar_replace(word) for word in words]

    # Juntar todas as palavras codificadas em uma frase
    coded_phrase = " ".join(coded_words)

    print("Original:", phrase)
    print("Coded:", coded_phrase)

if __name__ == "__main__":
    main()
```