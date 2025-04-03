# **Tratamento de exceções na manipulação de arquivos**

## 1. Tratamento de Exceções

O tratamento de exceções na manipulação de arquivos é fundamental para evitar falhas inesperadas e garantir que o programa continue funcionando de maneira controlada. Problemas como arquivos inexistentes ou falta de permissão podem ser resolvidos usando **blocos try/except**, permitindo um gerenciamento eficiente dos erros.

Ao executar operações com arquivos, erros como **FileNotFoundError** e **PermissionError** podem surgir. Esses problemas ocorrem em tempo de execução e, sem tratamento adequado, podem interromper o fluxo do programa.

O Python permite verificar na documentação oficial quais exceções podem ser lançadas por determinadas funções. O tratamento dessas exceções consiste em orientar o interpretador sobre qual ação tomar em caso de erro.

- Se um arquivo que deveria ser lido não existir, o Python lançará um **FileNotFoundError**, interrompendo o programa.

### Uso de try/except

Para evitar interrupções indesejadas, utilizamos a estrutura:

```python
try:
    arquivo = open("teste.txt", "r")
except FileNotFoundError:
    print("Arquivo inexistente")
```

Dessa forma, o Python identifica a falha e executa o código alternativo definido no `except`.

Isso garante que o programa siga funcionando mesmo quando ocorre um erro.

### Exceções Específicas Relacionadas a Arquivos

- **PermissionError**: Quando não há permissão para modificar ou acessar um arquivo.
- **FileExistsError**: Quando tentamos criar um arquivo ou diretório que já existe.
- **FileNotFoundError**: Quando tentamos abrir um arquivo que não existe.

Essas exceções herdam da classe **OSError**, que por sua vez herda de **Exception**.

**Boa prática:** Evite usar exceções genéricas como `except Exception`, pois isso pode ocultar erros inesperados.

### Exemplo de PermissionError

Caso um arquivo esteja sendo usado por outro programa, a tentativa de escrita pode falhar, gerando um **PermissionError**. Para lidar com isso:

```python
try:
    arquivo = open("bloqueado.pdf", "w")
except PermissionError:
    print("Permissão negada para modificar o arquivo.")
```

---
## 2. Operações Adicionais em Arquivos

Manipular arquivos em Python envolve não apenas leitura e escrita, mas também operações como remoção e renomeação. Essas ações são essenciais para organização de dados e automação de tarefas, garantindo um fluxo de trabalho mais eficiente e seguro.

### Removendo Arquivos

A função `remove` do módulo `os` permite excluir arquivos do sistema. Sua sintaxe é:

```python
import os
os.remove("teste.txt")  # Remove o arquivo especificado
```

Se o arquivo não estiver no diretório atual, é necessário informar o caminho completo.

Possíveis Exceções:

- **FileNotFoundError** – O arquivo não existe.
- **PermissionError** – O acesso ao arquivo é restrito.
- **IsADirectoryError** – A função foi usada em um diretório, em vez de um arquivo.

> *Para remover diretórios, use `os.rmdir()`.*

### Renomeando Arquivos

A função `rename` do módulo `os` permite renomear arquivos. Sua sintaxe é:

```python
import os
os.rename("teste_alfa.txt", "teste_beta.txt")  # Renomeia o arquivo
```

O primeiro argumento é o nome original, e o segundo é o novo nome.

Possíveis Exceções:

- **FileNotFoundError** – O arquivo de origem não existe.
- **FileExistsError** – O nome de destino já existe.
- **PermissionError** – Sem permissão para modificar o arquivo.

> *Caso seja necessário substituir o arquivo de destino, utilize `os.replace()`.*

---
## 3. Manipulação de Diretórios em Python

A organização de diretórios é essencial para estruturar arquivos e automatizar processos. Python oferece funções para criar, remover e listar diretórios, garantindo um ambiente eficiente para desenvolvimento.

### Criando e Removendo Diretórios

O módulo `os` fornece funções para gerenciar diretórios:

#### ***Criar um diretório** – `mkdir()`*

```python
import os
os.mkdir("meu_diretorio")  # Cria um diretório
```

Possíveis erros:

- **PermissionError** – Sem permissão para criar o diretório.
- **FileExistsError** – O diretório já existe.

#### ***Remover um diretório** – `rmdir()`*

```python
os.rmdir("meu_diretorio")  # Remove um diretório vazio
```

Possíveis erros:

- **PermissionError** – Sem permissão para remoção.
- **FileNotFoundError** – O diretório não existe.
- **OSError** – O diretório não está vazio.

>*Caso o erro seja **OSError**, é necessário verificar seu código por meio do atributo `errno` para entender sua causa.*

### Listando Conteúdo de Diretórios

Para visualizar arquivos e subdiretórios, utilizamos `scandir()`:

```python
entradas = os.scandir("meu_diretorio")
for entrada in entradas:
    print(entrada.name, "é diretório?" , entrada.is_dir())
```

A função retorna objetos `os.DirEntry`, que possuem métodos úteis:

- **name** – Nome do arquivo ou diretório.
- **path** – Caminho completo.
- **is_dir()** – Verifica se é um diretório.
- **is_file()** – Verifica se é um arquivo.