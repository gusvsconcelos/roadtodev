# **Conexão, Acesso e Criação de Banco de Dados em Python**

## 1. Conexão e Criação de Tabelas

### Estabelecendo Conexão com o Banco

- **Arquivo físico**: Cria ou abre um banco `.db`

```python
import sqlite3
conexao = sqlite3.connect("meu_banco.db")
```

- **Memória RAM (temporário)**:

```python
conexao = sqlite3.connect(":memory:")
```

### Modelo Entidade-Relacionamento

**Entidades:** `Pessoa`, `Marca`, `Veiculo`
**Relacionamentos:**

- Pessoa ↔ Veículo (1:N)
- Marca ↔ Veículo (1:N)

### Criação de Tabelas (SQL)

**Pessoa**

```sql
CREATE TABLE Pessoa (
    CPF INTEGER PRIMARY KEY NOT NULL,
    Nome TEXT NOT NULL,
    Nascimento DATE,
    Oculos BOOLEAN
);
```

**Marca**

```sql
CREATE TABLE Marca (
    Id INTEGER PRIMARY KEY NOT NULL,
    Nome TEXT NOT NULL,
    Sigla CHARACTER(2) NOT NULL
);
```

**Veículo**

```sql
CREATE TABLE Veiculo (
    Placa CHARACTER(7) PRIMARY KEY NOT NULL,
    Ano INTEGER,
    Cor TEXT,
    Proprietario INTEGER,
    Marca INTEGER,
    FOREIGN KEY (Proprietario) REFERENCES Pessoa(CPF),
    FOREIGN KEY (Marca) REFERENCES Marca(Id)
);
```

### Criando Tabelas via Python

```python
cursor = conexao.cursor()
cursor.execute("""
    CREATE TABLE Pessoa (
        CPF INTEGER PRIMARY KEY NOT NULL,
        Nome TEXT NOT NULL,
        Nascimento DATE,
        Oculos BOOLEAN
    );
""")
conexao.commit()
cursor.close()
conexao.close()
```

### Tratamento de Exceções

```python
try:
    ...
except sqlite3.DatabaseError:
    print("Erro geral no banco.")
except sqlite3.ProgrammingError:
    print("Erro de sintaxe ou chave estrangeira.")
```

### Visualização das Tabelas

> *💡 Use o **DB Browser for SQLite** para inspecionar seu `.db`.*

---
## 2. Alteração e Remoção de Tabelas

### Adicionando Atributos com `ALTER TABLE`

```sql
ALTER TABLE Veiculo ADD COLUMN motor REAL;
```

```python
cursor.execute("ALTER TABLE Veiculo ADD COLUMN motor REAL;")
```

### Recriando Tabela (quando `ALTER` não resolve)

```sql
DROP TABLE IF EXISTS Veiculo;
```

```sql
CREATE TABLE Veiculo (
    Placa CHARACTER(7) PRIMARY KEY NOT NULL,
    Ano INTEGER,
    Cor TEXT,
    Motor REAL,
    Proprietario INTEGER,
    Marca INTEGER,
    FOREIGN KEY (Proprietario) REFERENCES Pessoa(CPF),
    FOREIGN KEY (Marca) REFERENCES Marca(Id)
);
```

```python
cursor.execute("DROP TABLE IF EXISTS Veiculo;")
cursor.execute("""... CREATE TABLE ...""")
```

### Alternativa Moderna: ORM

> *💡 Use libs como `SQLAlchemy` ou `Peewee` para abstrair SQL com classes Python.*

---
## 3. Script Python com Banco de Dados

### Passo 1: Função de Conexão

```python
def conectar_banco():
    return sqlite3.connect("eventos.db")
```

### Passo 2: Função de Criação de Tabelas

```python
def criar_tabelas(conexao):
    cursor = conexao.cursor()

    cursor.execute("""
        CREATE TABLE IF NOT EXISTS Locais (
            id INTEGER PRIMARY KEY AUTOINCREMENT,
            nome TEXT NOT NULL,
            endereco TEXT
        );
    """)
    cursor.execute("""
        CREATE TABLE IF NOT EXISTS Eventos (
            id INTEGER PRIMARY KEY AUTOINCREMENT,
            nome TEXT NOT NULL,
            data TEXT,
            local_id INTEGER,
            FOREIGN KEY (local_id) REFERENCES Locais(id)
        );
    """)
    cursor.execute("""
        CREATE TABLE IF NOT EXISTS Participantes (
            id INTEGER PRIMARY KEY AUTOINCREMENT,
            nome TEXT NOT NULL,
            evento_id INTEGER,
            FOREIGN KEY (evento_id) REFERENCES Eventos(id)
        );
    """)
    conexao.commit()
```

### Passo 3: Script Principal

```python
if __name__ == "__main__":
    conexao = conectar_banco()
    criar_tabelas(conexao)
    conexao.close()
    print("Banco de dados inicializado com sucesso!")
```

### Passo 4: Execução

```bash
python gerenciamento_eventos.py
```

**Resultado esperado**:
- Criação do arquivo `eventos.db`
- Tabelas criadas com sucesso
- Mensagem de confirmação no terminal