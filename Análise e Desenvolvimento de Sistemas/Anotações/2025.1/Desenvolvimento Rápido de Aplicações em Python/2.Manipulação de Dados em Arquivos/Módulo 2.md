# **Funções de manipulação de strings**

## 1. Manipulação de strings

Operações como remoção de espaços, conversão entre maiúsculas e minúsculas e substituição de caracteres são ferramentas essenciais para preparar e processar dados de forma eficiente e precisa.

- Método **strip**
- Método **count**
- Método **split**
- Método **join**

### Método *strip*

`strip()` remove espaços extras e caracteres de fim de linha no início e final de uma string. É útil, por exemplo, para limpar dados ao processar linhas de um arquivo.  

**Uso prático do `strip()`:** linhas lidas frequentemente possuem espaços extras ou quebras de linha indesejadas. O método `strip()` ajuda a "limpar" essas linhas antes de armazená-las ou processá-las.

### Método *count*

O método `count()` é usado para contar o número de vezes que uma palavra ou trecho específico aparece em uma string.

- É prático, mas pode apresentar resultados inesperados ao contar substrings que estão dentro de outras palavras.

**Frase**: `"Eu amo comer amoras no café da manhã"`

- Contando `"amo"` com `count()`, o retorno será **2**, pois `"amo"` está em **"amo"** e **"amoras"**.

**Solução para maior precisão:** É possível usar o método `split()`, quebrando a frase em palavras e verificando cada uma individualmente.

### Método *split*

O método `split()` divide uma string em uma lista de partes menores com base em um delimitador (ou separador).  

- Sem delimitador: usa espaço como separador padrão.
- Com delimitador: ignora o separador na lista resultante.

**Frase**: `"Carro,moto,avião"`

- Resultado de `split(',')`: `["Carro", "moto", "avião"]`

#### Comparação *count* vs. *split* na contagem de palavras

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