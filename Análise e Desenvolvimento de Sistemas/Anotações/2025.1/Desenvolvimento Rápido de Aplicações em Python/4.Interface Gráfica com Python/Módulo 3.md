# **Integração com Banco de Dados usando PostgreSQL + psycopg2**

## 1. Visão Geral da Integração

Você vai criar um CRUD de agenda telefônica com Python e PostgreSQL, usando a biblioteca **psycopg2** para gerenciar os dados via SQL.

> *📞 Objetivo: cadastrar, consultar, atualizar e remover nomes e telefones de uma agenda.*

---
## 2. Ferramentas Utilizadas

- **PostgreSQL**: SGBD relacional robusto e gratuito.
- **psycopg2**: Adaptador que conecta Python ao PostgreSQL.

### Instalação

```bash
pip install psycopg2
```

---
## 3. Conectando ao Banco

```python
import psycopg2

conexao = psycopg2.connect(
    host="localhost",
    database="nome_do_banco",
    user="usuario",
    password="senha"
)

cursor = conexao.cursor()
```

> *🔐 Você precisa estar com o servidor PostgreSQL rodando localmente.*

---
## 4. Operações CRUD com psycopg2

### Criar Tabela

```python
cursor.execute("""
CREATE TABLE agenda (
    id SERIAL PRIMARY KEY,
    nome VARCHAR(100),
    telefone VARCHAR(15)
)
""")
conexao.commit()
```

### Inserir Dados

```python
cursor.execute("""
INSERT INTO agenda (nome, telefone)
VALUES (%s, %s)
""", ("João Silva", "123456789"))
conexao.commit()
```

> *⚠️ Use parâmetros (%s) para evitar SQL Injection.*

### Consultar Dados

```python
cursor.execute("SELECT * FROM agenda")
resultados = cursor.fetchall()

for linha in resultados:
    print(linha)
```

### Atualizar Dados

```python
cursor.execute("""
UPDATE agenda
SET telefone = %s
WHERE nome = %s
""", ("987654321", "João Silva"))
conexao.commit()
```

### Deletar Dados

```python
cursor.execute("""
DELETE FROM agenda
WHERE nome = %s
""", ("João Silva",))
conexao.commit()
```

> 🗑️ _Use `rowcount` para verificar quantos registros foram excluídos._

---
## 5. Encerrando a Conexão

```python
cursor.close()
conexao.close()
```

> *🧼 Fechar conexão = boa prática obrigatória.*

---
## 6. Funções Extras do psycopg2

- `cursor.callproc(nome_funcao, args)` → Chama função armazenada.
- `cursor.rowcount` → Retorna linhas afetadas.
- `cursor.fetchone()` → Retorna uma linha.
- `cursor.fetchmany(n)` → Retorna n linhas.
- `cursor.fetchall()` → Retorna todas as linhas restantes.
- `connection.commit()` → Salva mudanças.
- `connection.rollback()` → Cancela mudanças pendentes.

---
## 7. Exemplo Prático Completo

```python
import psycopg2

con = psycopg2.connect(
    dbname="sua_agenda",
    user="seu_usuario",
    password="sua_senha",
    host="localhost"
)

cursor = con.cursor()

cursor.execute("""
CREATE TABLE IF NOT EXISTS agenda (
    id SERIAL PRIMARY KEY,
    nome VARCHAR(50),
    telefone VARCHAR(15)
)
""")
con.commit()

cursor.execute("""
INSERT INTO agenda (nome, telefone)
VALUES ('Pessoa 1', '02199999999')
""")

cursor.execute("SELECT * FROM agenda WHERE nome = 'Pessoa 1'")
print(cursor.fetchone())

cursor.execute("""
UPDATE agenda
SET telefone = '02198888888'
WHERE nome = 'Pessoa 1'
""")
con.commit()

cursor.execute("DELETE FROM agenda WHERE nome = 'Pessoa 1'")
print(f"{cursor.rowcount} registro(s) excluído(s).")

cursor.close()
con.close()
```

---
## 8. Outras Bibliotecas para Outros SGBDs

> *🧰 Use a ferramenta certa para o banco certo:*

- `pyMySQL` → MySQL/MariaDB
- `cx_Oracle` → Oracle
- `sqlite3` (nativo) → SQLite
- `PyMongo` → MongoDB (NoSQL)