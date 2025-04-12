# **Integração com banco de dados**

## 1. Conceitos de integração com banco de dados

A capacidade de executar operações CRUD (Create, Read, Update, Delete) diretamente do Python para gerenciar dados em um banco otimiza processos e facilita a gestão de grandes volumes de informações.

### Conceitos

Para entender como Python interage com PostgreSQL, trabalharemos na seguinte aplicação:

**Objetivo**: Um programa CRUD para gerenciar uma agenda telefônica (com nomes e números de telefone) utilizando PostgreSQL como banco de dados.

### Ferramentas e Tecnologias Utilizadas

1. **PostgreSQL**: Instale a versão recomendada (ex.: 4.24).
2. **Biblioteca psycopg2**: Adaptador para conectar Python ao PostgreSQL.

#### *Instalação do psycopg2*

Para instalar, digite na linha de comando:

```bash
pip install psycopg2
```

### APIs e Operações no PostgreSQL com psycopg2

#### *Criar Conexão e Cursor*

Antes de executar qualquer operação, crie uma conexão com o banco e um cursor para realizar as instruções SQL:

```python
import psycopg2

# Estabelecendo a conexão com o banco de dados
connection = psycopg2.connect(
    host="localhost",
    database="seu_banco",
    user="seu_usuario",
    password="sua_senha"
)

# Criando um cursor
cursor = connection.cursor()
```

#### *Criar uma Tabela*

```python
# Criando uma tabela
cursor.execute("""
CREATE TABLE agenda (
    id SERIAL PRIMARY KEY,
    nome VARCHAR(100),
    telefone VARCHAR(15)
)
""")

# Confirmando a transação
connection.commit()
```

#### *Inserir Dados*

```python
# Inserindo dados na tabela
cursor.execute("""
INSERT INTO agenda (nome, telefone)
VALUES (%s, %s)
""", ("João Silva", "123456789"))

# Confirmando a transação
connection.commit()
```

#### *Consultar Dados*

```python
# Consultando dados
cursor.execute("""
SELECT * FROM agenda
""")

# Obtendo todos os resultados
resultados = cursor.fetchall()
for linha in resultados:
    print(linha)
```

#### *Atualizar Dados*

```python
# Atualizando dados
cursor.execute("""
UPDATE agenda
SET telefone = %s
WHERE nome = %s
""", ("987654321", "João Silva"))

# Confirmando a transação
connection.commit()
```

#### *Deletar Dados*

```python
# Deletando dados
cursor.execute("""
DELETE FROM agenda
WHERE nome = %s
""", ("João Silva",))

# Confirmando a transação
connection.commit()
```

#### *Fechar Cursor e Conexão*

```python
# Fechar cursor e conexão
cursor.close()
connection.close()
```

### Principais Funções e Rotinas

- **cursor.callproc**: Chama funções/procedimentos armazenados.
- **cursor.rowcount**: Total de linhas afetadas pela última operação.
- **connection.commit()**: Confirma a transação.
- **connection.rollback()**: Reverte alterações desde o último commit.
- **cursor.fetchone()**: Retorna a próxima linha do resultado.
- **cursor.fetchmany(size)**: Retorna várias linhas (tamanho definido).
- **cursor.fetchall()**: Retorna todas as linhas restantes do resultado.

---
## 2. Integração com banco de dados com psycopg2

### Principais Benefícios

- **Manipulação direta** de dados via scripts Python.
- **Automatização** de tarefas repetitivas.
- Ideal para criar **soluções complexas** com persistência de dados.

### Exemplo Completo de Operações CRUD

#### *1. Criação de Tabela*

```python
import psycopg2

conexao = psycopg2.connect(
    dbname="nome_do_banco",
    user="usuario",
    password="senha",
    host="localhost"
)
cursor = conexao.cursor()

cursor.execute("""
CREATE TABLE Agenda (
    ID SERIAL PRIMARY KEY,
    Nome VARCHAR(50),
    Telefone VARCHAR(15)
)
""")
conexao.commit()
conexao.close()
```

#### *2. Inserção de Dados*

```python
cursor.execute("""
INSERT INTO Agenda (ID, Nome, Telefone)
VALUES (1, 'Pessoa 1', '02199999999')
""")
```

**Cuidados**: Use aspas duplas para nomes de tabelas e colunas no PostgreSQL.

#### *3. Seleção de Dados*

```python
cursor.execute("SELECT * FROM Agenda WHERE ID = 1")
registro = cursor.fetchone()
print(registro)
```

**Resultado esperado**: `(1, 'Pessoa 1', '02199999999')`

#### *4. Atualização de Dados*

```python
cursor.execute("""
UPDATE Agenda
SET Telefone = '02198888888'
WHERE ID = 1
""")
conexao.commit()
```

#### *5. Exclusão de Dados*

```python
cursor.execute("""
DELETE FROM Agenda WHERE ID = 1
""")
print(f"{cursor.rowcount} Registro excluído com sucesso!")
```

### Outras Bibliotecas Populares para Banco de Dados

- **pyMySQL**: Para MySQL.
- **cx_Oracle**: Para Oracle.
- **PySQLite**: Para SQLite.
- **PyMongo**: Para MongoDB (NoSQL).