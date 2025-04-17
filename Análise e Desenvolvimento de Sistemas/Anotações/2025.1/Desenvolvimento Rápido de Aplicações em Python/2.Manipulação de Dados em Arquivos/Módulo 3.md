# **Tratamento de Exceções na Manipulação de Arquivos**

## 1. Tratamento de Exceções

> *🎯 Evitar crashes por erro de leitura/escrita é questão de sobrevivência em sistemas reais.*

**Cenários comuns de erro**:

- Arquivo inexistente → `FileNotFoundError`
- Falta de permissão → `PermissionError`
- Arquivo já existe → `FileExistsError`

### Try/Except Básico

```python
try:
    arquivo = open("teste.txt", "r")
except FileNotFoundError:
    print("Arquivo inexistente.")
```

> *✅ Garante continuidade do programa mesmo após erro.*

### Exceções específicas

| Erro                | Quando acontece                    |
| ------------------- | ---------------------------------- |
| `FileNotFoundError` | Arquivo não existe                 |
| `PermissionError`   | Sem permissão para abrir/modificar |
| `FileExistsError`   | Arquivo/diretório já existe        |

- Todas são subclasses de `OSError`

> *🧼 Evite `except Exception` genérico. Isso esconde bugs feios.*

### Exemplo: `PermissionError`

```python
try:
    open("arquivo_trancado.txt", "w")
except PermissionError:
    print("Permissão negada.")
```

---
## 2. Operações Adicionais com Arquivos

### Removendo Arquivos

```python
import os
os.remove("teste.txt")
```

**Possíveis exceções**:

- `FileNotFoundError`
- `PermissionError`
- `IsADirectoryError`

> *📦 Para remover diretórios: `os.rmdir()`.*

### Renomeando Arquivos

```python
os.rename("alfa.txt", "beta.txt")
```

**Exceções**:

- Arquivo não existe → `FileNotFoundError`
- Nome já existe → `FileExistsError`
- Sem permissão → `PermissionError`

> *🔁 Para substituir um arquivo existente: `os.replace()`.*

---
## 3. Manipulação de Diretórios

### Criar Diretório

```python
os.mkdir("novo_diretorio")
```

**Erros comuns**:

- `PermissionError`
- `FileExistsError`

### Remover Diretório (vazio)

```python
os.rmdir("diretorio_vazio")
```

**Possíveis erros**:

- `PermissionError`
- `FileNotFoundError`
- `OSError` (caso não esteja vazio)

> *🔍 Se for `OSError`, use `errno` para diagnosticar.*

### Listar Conteúdo de Diretório

```python
entradas = os.scandir("meu_diretorio")
for entrada in entradas:
    print(entrada.name, "é diretório?", entrada.is_dir())
```

**Métodos úteis de `DirEntry`**:

- `.name` – Nome do item
- `.path` – Caminho completo
- `.is_dir()` – É diretório?
- `.is_file()` – É arquivo?