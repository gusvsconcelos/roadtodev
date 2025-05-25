# **Recuperação de Registros no SQLite com Python**

## 1. Seleção Simples com `SELECT`

### Conceito

- O comando `SELECT` é usado para consultar dados em tabelas.
- Permite filtros, projeções e manipulações.

### Sintaxe Geral

```sql
SELECT colunas FROM tabela WHERE condição;
```

- `*` seleciona todas as colunas.
- `WHERE` é opcional, mas essencial para filtros.

### Exemplo 1: Recuperando Campos Específicos

**SQL**

```sql
SELECT Nome, Oculos FROM Pessoa;
```

**Python**

```python
conexao = sqlite3.connect("meu_banco.db")
cursor = conexao.cursor()

cursor.execute("SELECT Nome, Oculos FROM Pessoa;")
registros = cursor.fetchall()

for nome, oculos in registros:
    print(f"Nome: {nome}, Óculos: {oculos}")

cursor.close()
conexao.close()
```

**Saída**

```
Nome: Maria, Óculos: 0
Nome: João, Óculos: 1
Nome: Silva, Óculos: 1
```

### Exemplo 2: Aplicando Filtro com `WHERE`

```sql
SELECT * FROM Pessoa WHERE Oculos = 1;
```

**Python**

```python
cursor.execute("SELECT * FROM Pessoa WHERE Oculos = ?;", (1,))
resultados = cursor.fetchall()

for cpf, nome, nascimento, oculos in resultados:
    print(f"{nome} ({cpf}) - Óculos: {oculos}")
```

---
## 2. Conversão de Tipos com Python

### Objetivo

- Converter tipos SQLite (`DATE`, `BOOLEAN`) em objetos Python.

### Configuração

```python
import sqlite3

def conv_bool(valor):
    return valor == 1

sqlite3.register_converter("BOOLEAN", conv_bool)

conexao = sqlite3.connect("meu_banco.db", detect_types=sqlite3.PARSE_DECLTYPES)
```

### Consulta com Tipagem Convertida

```python
cursor = conexao.cursor()
cursor.execute("SELECT * FROM Pessoa WHERE Oculos = ?", (1,))
pessoas = cursor.fetchall()

for pessoa in pessoas:
    print(pessoa)  # Boolean convertido, data como datetime.date
```

> *📌 Use `detect_types=sqlite3.PARSE_DECLTYPES` + `register_converter` para conversões automáticas.*

---
## 3. Junções com `JOIN` (Relacionamentos)

### Conceito

- `JOIN` permite combinar dados de múltiplas tabelas relacionadas.

### Sintaxe Base

```sql
SELECT tabela1.coluna1, tabela2.coluna2
FROM tabela1
JOIN tabela2
ON tabela1.chave = tabela2.chave;
```

### Exemplo 1: Veículos e suas Marcas

**SQL**

```sql
SELECT Veiculo.Placa, Marca.Nome
FROM Veiculo
JOIN Marca ON Veiculo.Marca = Marca.Id;
```

**Python**

```python
cursor.execute("""
SELECT Veiculo.Placa, Marca.Nome
FROM Veiculo
JOIN Marca ON Veiculo.Marca = Marca.Id;
""")

for placa, marca in cursor.fetchall():
    print(f"Placa: {placa}, Marca: {marca}")
```

### Exemplo 2: Junção com Objetos Python

```python
cursor.execute("""
SELECT Veiculo.*, Marca.*
FROM Veiculo
JOIN Marca ON Veiculo.Marca = Marca.Id;
""")

for registro in cursor.fetchall():
    marca = Marca(*registro[6:9])  # Marca: colunas 6 a 8
    veiculo = Veiculo(*registro[:5], marca)  # Veiculo: colunas 0 a 4
    print(f"{veiculo.Placa} - {veiculo.Marca.Nome}")
```

> *🧩 Usamos array slicing para separar os campos de cada entidade.*

---
## 4. Seleção de Registros Relacionados por Pessoa

### Objetivo

- Exibir todas as pessoas com seus veículos e respectivas marcas.

### Função Auxiliar: Veículos de uma Pessoa

```python
def recuperar_veiculos(conexao, cpf):
    cursor = conexao.cursor()
    cursor.execute("""
    SELECT Veiculo.Placa, Marca.Nome
    FROM Veiculo
    JOIN Marca ON Veiculo.Marca = Marca.Id
    WHERE Veiculo.Proprietario = ?;
    """, (cpf,))
    
    veiculos = [Veiculo(placa, marca) for placa, marca in cursor.fetchall()]
    cursor.close()
    return veiculos
```

### Script Principal

```python
conexao = sqlite3.connect("meu_banco.db")
cursor = conexao.cursor()

cursor.execute("SELECT * FROM Pessoa;")
pessoas = cursor.fetchall()

for dados in pessoas:
    pessoa = Pessoa(*dados)
    pessoa.veiculos = recuperar_veiculos(conexao, pessoa.cpf)
    print(f"{pessoa.Nome}")
    for v in pessoa.veiculos:
        print(f"{v.Placa} {v.Marca}")

cursor.close()
conexao.close()
```

### Saída Esperada

```
Maria
AAA0001 Marca A
BAA0002 Marca A

José
CAA0003 Marca B

Silva
DAA0004 Marca B
```