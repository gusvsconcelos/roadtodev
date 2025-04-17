# **Inserção, Atualização e Remoção de Dados com SQLite e Python**

## 1. Inserção de Dados com SQL Fixo

### Conceito

- Inserção direta com o comando `INSERT INTO`.
- Ideal para testes ou inserções simples.

### Sintaxe SQL

```sql
INSERT INTO Pessoa (CPF, Nome, Nascimento, Oculos)
VALUES (12345678900, 'João', '2000-01-31', 1);
```

> *🟡 Datas devem estar no formato ISO (`YYYY-MM-DD`)*

> *🟢 Valores bool são convertidos para integer (1 = True, 0 = False)*

### Exemplo com Python

```python
import sqlite3

conexao = sqlite3.connect("meu_banco.db")
cursor = conexao.cursor()

comando = """
INSERT INTO Pessoa (CPF, Nome, Nascimento, Oculos)
VALUES (12345678900, 'João', '2000-01-31', 1);
"""

cursor.execute(comando)
conexao.commit()
cursor.close()
conexao.close()
```

---
## 2. Inserção com Queries Dinâmicas e Delimitadores `?`

### Conceito

- Substitui valores diretamente com `?` para segurança.
- Evita SQL Injection e facilita automação.

### Etapas

1. Cria-se a query com `?` como placeholders.
2. Os valores são passados como tupla.

### Exemplo

```python
class Pessoa:
    def __init__(self, cpf, nome, nascimento, oculos):
        self.cpf = cpf
        self.nome = nome
        self.nascimento = nascimento
        self.oculos = oculos

nova_pessoa = Pessoa(10000000099, 'Maria', '1990-01-31', False)

conexao = sqlite3.connect("meu_banco.db")
cursor = conexao.cursor()

comando = """
INSERT INTO Pessoa (CPF, Nome, Nascimento, Oculos)
VALUES (?, ?, ?, ?);
"""

cursor.execute(comando, (nova_pessoa.cpf, nova_pessoa.nome, nova_pessoa.nascimento, nova_pessoa.oculos))
conexao.commit()
cursor.close()
conexao.close()
```

> *✅ Uso de tupla → segura, legível e reaproveitável*

---
## 3. Inserção com Argumentos Nomeados (`:campo`)

### Conceito

- Permite associação explícita entre campos e valores.
- Facilita manutenções em códigos com muitos atributos.

### Sintaxe

```sql
INSERT INTO Pessoa (CPF, Nome, Nascimento, Oculos)
VALUES (:cpf, :nome, :nascimento, :oculos);
```

### Exemplo com Python

```python
pessoa = Pessoa(20000000099, 'José', '1990-02-28', False)

comando = """
INSERT INTO Pessoa (CPF, Nome, Nascimento, Oculos)
VALUES (:cpf, :nome, :nascimento, :oculos);
"""

cursor.execute(comando, {
    'cpf': pessoa.cpf,
    'nome': pessoa.nome,
    'nascimento': pessoa.nascimento,
    'oculos': pessoa.oculos
})
```

### Otimização com `vars()`

```python
comando = "INSERT INTO Pessoa VALUES (:cpf, :nome, :nascimento, :oculos);"
cursor.execute(comando, vars(pessoa))
```

> *⚡ `vars()` transforma os atributos da classe em um dicionário automaticamente.*

---
## 4. Inserção com Chave Estrangeira

### Conceito

- Só é possível inserir registros relacionados se as chaves estrangeiras existirem.
- Caso contrário, ocorre erro de integridade.

### Etapas

1. **Ativar FK no SQLite**

```python
cursor.execute("PRAGMA foreign_keys = ON;")
```

2. **Inserir marca (FK principal)**

```python
marca = {'nome': 'Toyota', 'sigla': 'TY'}
cursor.execute("INSERT INTO Marca (Nome, Sigla) VALUES (:nome, :sigla);", marca)
marca_id = cursor.lastrowid
```

3. **Usar o ID na inserção de veículo**

```python
veiculo = {'placa': 'XYZ1234', 'ano': 2020, 'cor': 'Vermelho', 'marca': marca_id, 'proprietario': 12345678900}
cursor.execute("""
INSERT INTO Veiculo (Placa, Ano, Cor, Marca, Proprietario)
VALUES (:placa, :ano, :cor, :marca, :proprietario);
""", veiculo)
```

---
## 5. Atualização de Dados com `UPDATE`

### Conceito

- Modifica valores de colunas em registros existentes.

### Sintaxe

```sql
UPDATE tabela SET coluna = novo_valor WHERE condição;
```

> *⚠️ Sempre use cláusula `WHERE` para evitar atualizações em massa!*

### Exemplos com Python

```python
cursor.execute("UPDATE Pessoa SET Oculos = 1;")  # Atualiza todos
cursor.execute("UPDATE Pessoa SET Oculos = ? WHERE CPF = ?;", (0, 30000000099))
cursor.execute("UPDATE Pessoa SET Oculos = :oculos WHERE CPF = :cpf;", {'oculos': 0, 'cpf': 20000000099})
```

---
## 6. Remoção de Dados com `DELETE`

### Conceito

- Remove registros de uma tabela.

### Sintaxe

```sql
DELETE FROM tabela WHERE condição;
```

### Exemplos com Python

```python
cursor.execute("DELETE FROM Pessoa WHERE CPF = 12345678900;")
cursor.execute("DELETE FROM Pessoa WHERE CPF = :cpf;", {'cpf': 20000000099})
```

> *⚠️ Registros vinculados por FK não podem ser removidos sem tratar dependências*