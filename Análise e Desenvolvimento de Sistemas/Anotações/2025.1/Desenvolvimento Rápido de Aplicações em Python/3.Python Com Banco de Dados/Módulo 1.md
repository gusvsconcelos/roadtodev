# **Frameworks e Bibliotecas para Gerenciamento de Dados**

## 1. Conectores para Banco de Dados

Conectores são bibliotecas que permitem que aplicações Python se comuniquem com diferentes SGBDs, seguindo a especificação PEP 249 (DB-API 2.0).

### Padrões Definidos pela DB-API 2.0:

- **Métodos**: `connect()`, `cursor()`, `commit()`, `close()`.
- **Classes**: `Connection`, `Cursor`.
- **Exceções**: `IntegrityError`, `OperationalError`, `DatabaseError`, etc.

### Principais Conectores

**PostgreSQL**

- `psycopg2` - Alta performance, suporte a recursos nativos.

**MySQL**

- `mysqlsclient` - Rápido, requer dependências nativas.
- `PyMySQL` - 100% Python, fácil instalação.
- `mysql-connector-python` - Suporte oficial da Oracle.

**SQLite**

- `sqlite3` - Integrado ao Python, ideal para apps locais.

### Por Que Usar Conectores?

- **Interface padronizada** entre Python e o banco.
- **Portabilidade entre SGBDs**.
- **Execução simplificada de operações CRUD**.

### Critérios de Escolha

- Compatibilidade com o SGBD.
- Facilidade de instalação.
- Suporte oficial e comunidade.
- Recursos específicos (ex: transações, prepared statements).

---
## 2. Métodos e Exceções dos Conectores

==Todos os conectores seguem um fluxo operacional básico e disparam exceções específicas para controle de erros.==

### Fluxo Padrão de Uso

```python
import sqlite3

con = sqlite3.connect("banco.db")
cur = con.cursor()

cur.execute("CREATE TABLE exemplo (id INTEGER, nome TEXT)")
cur.execute("INSERT INTO exemplo VALUES (1, 'Python')")

con.commit()
cur.close()
con.close()
```

### Principais Exceções

| **Exceção**         | **Situação**                                  |
| ------------------- | --------------------------------------------- |
| `Error`             | Base para todas as exceções.                  |
| `IntegrityError`    | Violação de restrições (ex: chave duplicada). |
| `OperationalError`  | Falhas de conexão ou problemas operacionais.  |
| `DatabaseError`     | Erros gerais do banco.                        |
| `ProgrammingError`  | SQL inválido ou sintaxe errada.               |
| `NotSupportedError` | Função não suportada pelo SGBD.               |

### Tratamento de Erros

```python
try:
    conexao = sqlite3.connect("banco.db")
    cursor = conexao.cursor()
    cursor.execute("INSERT INTO exemplo VALUES (1, 'Python')")
    conexao.commit()
except sqlite3.IntegrityError:
    print("Erro: dado duplicado.")
except sqlite3.OperationalError as e:
    print(f"Erro operacional: {e}")
finally:
    if conexao:
        conexao.close()
```

### Portabilidade e Flexibilidade

- O mesmo fluxo funciona com `psycopg2`, `mysql.connector`, `PyMySQL`, etc.
- Alterar o conector = mudar só a importação.

---
## 3. Tipos de Dados

O uso correto dos tipos de dados impacta diretamente a performance, integridade e compatibilidade do banco.

### Tipos Comuns

| **Tipo**  | **Uso**                            |
| --------- | ---------------------------------- |
| `INTEGER` | Números inteiros                   |
| `REAL`    | Ponto flutuante                    |
| `TEXT`    | Strings e dados alfanuméricos      |
| `BLOB`    | Dados binários (imagens, arquivos) |
| `NULL`    | Valores indefinidos                |

---
## 4. Particularidades do SQLite

O SQLite é mais permissivo e utiliza o conceito de _afinidade de tipos_.

### Classes de Armazenamento

- `NULL`
- `INTEGER`
- `REAL`
- `TEXT`
- `BLOB`

### Afinidade de Tipos

| **Afinidade** | **Tipos Convertidos**                   |
| ------------- | --------------------------------------- |
| TEXT          | `CHAR`, `VARCHAR`, `TEXT`, `CLOB`       |
| NUMERIC       | `BOOLEAN`, `DATE`, `DECIMAL`, `NUMERIC` |
| INTEGER       | `INT`, `TINYINT`, `BIGINT`              |
| REAL          | `FLOAT`, `DOUBLE`                       |
| NONE          | Sem conversão, aceita qualquer tipo     |

### Exemplo de Mapeamento

```sql
CREATE TABLE produto (
    id INTEGER PRIMARY KEY,
    nome VARCHAR(100),
    preco DECIMAL(10, 2),
    imagem BLOB
);
```

**SQLite interpreta isso como:**

- `VARCHAR(100)` → `TEXT`
- `DECIMAL(10,2)` → `NUMERIC`
- `BLOB` → `BLOB`

### Em Desenvolvimento vs Produção

Mesmo em dev com SQLite, defina tipos pensando no deploy (ex: PostgreSQL ou MySQL).
    
- Isso garante **compatibilidade futura** com bancos reais.