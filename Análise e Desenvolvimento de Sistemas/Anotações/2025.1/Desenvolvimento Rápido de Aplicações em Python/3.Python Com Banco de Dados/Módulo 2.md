# **Conexão, acesso e criação de banco de dados**

## 1. Conexão a banco de dados e criação de tabelas

Conectar um script Python a um banco de dados e criar tabelas é essencial para organizar dados de forma estruturada, garantir integridade e viabilizar sistemas escaláveis.

### Conectando a um Banco de Dados

O SQLite permite criar e conectar a um banco de dados com simplicidade:

- **Conexão com banco de dados em arquivo**:

```python
import sqlite3
conexao = sqlite3.connect("meu_banco.db")  # Se o arquivo não existir, será criado
```

- **Banco de dados em memória** (temporário):

```python
conexao = sqlite3.connect(':memory:')
```

A conexão estabelecida está pronta para receber comandos SQL.

### Criando Tabelas

#### *Modelo Entidade-Relacionamento (ER)*

O exemplo utiliza três entidades: **Pessoa**, **Marca** e **Veículo**, com os seguintes relacionamentos:

- **Pessoa**: Pode ter zero ou mais veículos. Um veículo tem apenas um proprietário.
- **Marca**: Pode estar em zero ou mais veículos. Um veículo tem apenas uma marca.

#### *Tabela Pessoa*

**Atributos e tipos**:

- **CPF**: INTEGER, chave primária e não nulo.
- **Nome**: TEXT.
- **Nascimento**: DATE (convertido por afinidade para NUMERIC).
- **Óculos**: BOOLEAN (1 para True, 0 para False).

**Criação com SQL**:

```sql
CREATE TABLE Pessoa (
    CPF INTEGER PRIMARY KEY NOT NULL,
    Nome TEXT NOT NULL,
    Nascimento DATE,
    Oculos BOOLEAN
);
```

#### *Tabela Marca*

**Atributos e tipos**:

- **Id**: INTEGER, chave primária e não nulo.
- **Nome**: TEXT, não nulo.
- **Sigla**: CHARACTER(2) (convertido por afinidade para TEXT).

**Criação com SQL**:

```sql
CREATE TABLE Marca (
    Id INTEGER PRIMARY KEY NOT NULL,
    Nome TEXT NOT NULL,
    Sigla CHARACTER(2) NOT NULL
);
```

#### *Tabela Veículo*

**Atributos e tipos**:

- **Placa**: CHARACTER(7), chave primária e não nulo (convertido para TEXT).
- **Ano**: INTEGER.
- **Cor**: TEXT.
- **Proprietario**: INTEGER, chave estrangeira referenciando `Pessoa.CPF`.
- **Marca**: INTEGER, chave estrangeira referenciando `Marca.Id`.

**Criação com SQL**:

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

### Criação de Tabelas com Python

**Utilize os comandos SQL dentro de um script Python**:

```python
import sqlite3

# Conexão e cursor
conexao = sqlite3.connect("meu_banco.db")
cursor = conexao.cursor()

# Definição e execução do comando SQL
comando = """
CREATE TABLE Pessoa (
    CPF INTEGER PRIMARY KEY NOT NULL,
    Nome TEXT NOT NULL,
    Nascimento DATE,
    Oculos BOOLEAN
);
"""
cursor.execute(comando)

# Confirmar e encerrar conexão
conexao.commit()
cursor.close()
conexao.close()
```

### Tratamento de Exceções

Envolva o código em blocos `try/except` para capturar erros como:

- **DatabaseError**: Erros gerais do banco de dados.
- **ProgrammingError**: Chaves estrangeiras referenciadas incorretamente.

### Visualização das Tabelas

Use o **DB Browser for SQLite** para verificar as tabelas criadas:

1. Abra o programa.
2. Clique em "Abrir banco de dados" e selecione `meu_banco.db`

---
## 2. Alteração e remoção de tabela

Modificar e remover tabelas em bancos de dados é crucial para manter a estrutura flexível e adaptável ao longo do desenvolvimento. Os comandos `ALTER TABLE` e `DROP TABLE` permitem adicionar atributos e remover tabelas conforme necessário.

### Adicionando um Novo Atributo

O comando `ALTER TABLE` é utilizado para adicionar colunas em uma tabela existente. No exemplo, adicionamos o atributo `motor` à tabela `Veiculo`, do tipo **REAL**:

```sql
ALTER TABLE Veiculo ADD COLUMN motor REAL;
```

#### *Implementação em Python*

```python
import sqlite3

# Conectar ao banco de dados
conexao = sqlite3.connect("meu_banco.db")
cursor = conexao.cursor()

# Executar a alteração
comando = "ALTER TABLE Veiculo ADD COLUMN motor REAL;"
cursor.execute(comando)

# Confirmar e fechar conexão
conexao.commit()
cursor.close()
conexao.close()
```

A coluna `motor` será adicionada ao final da tabela.

### Removendo e Recriando uma Tabela

Se for necessário reordenar atributos na tabela, muitos SGBDs (incluindo SQLite) não suportam a mudança direta da ordem das colunas. Uma solução é **remover e recriar** a tabela.

#### *Removendo a tabela*

```sql
DROP TABLE IF EXISTS Veiculo;
```

#### *Recriando a tabela com os atributos na ordem desejada*

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

#### *Implementação em Python*

```python
# Remover tabela
cursor.execute("DROP TABLE IF EXISTS Veiculo;")

# Criar novamente com a ordem desejada
cursor.execute("""
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
""")

# Confirmar alteração e fechar conexão
conexao.commit()
cursor.close()
conexao.close()
```

### Mapeamento Objeto-Relacional (ORM)

Bibliotecas como **SQLAlchemy** e **Peewee** simplificam a interação com bancos de dados ao transformar tabelas em classes Python. Isso elimina a necessidade de escrever comandos SQL manualmente, permitindo operações por meio de métodos.

---
## 3. Desenvolvento um script Python com conexão a banco de dados

### Passo 1: Conectar-se ao Banco de Dados

Importe a biblioteca `sqlite3` e crie uma função para estabelecer a conexão:

```python
import sqlite3

def conectar_banco():
    conexao = sqlite3.connect("eventos.db")
    return conexao
```

### Passo 2: Criar as Tabelas

Defina uma função que cria as tabelas **Eventos**, **Participantes** e **Locais**, garantindo que o banco armazene as informações corretamente.

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

### Passo 3: Montar o Script Principal

No final do arquivo **gerenciamento_eventos.py**, inclua a lógica principal para conectar-se ao banco e criar as tabelas:

```python
if __name__ == "__main__":
    conexao = conectar_banco()
    criar_tabelas(conexao)
    conexao.close()
    print("Banco de dados inicializado com sucesso!")
```

### Passo 4: Executar o Script

Abra um terminal ou prompt de comando e navegue até o diretório onde o arquivo **gerenciamento_eventos.py** está salvo. Execute o script com o seguinte comando:

```bash
python gerenciamento_eventos.py
```

### Resultado Esperado

Após a execução do script:

- O banco de dados `eventos.db` será criado.
- As tabelas **Locais**, **Eventos** e **Participantes** serão geradas.
- O console exibirá a mensagem **"Banco de dados inicializado com sucesso!"**.