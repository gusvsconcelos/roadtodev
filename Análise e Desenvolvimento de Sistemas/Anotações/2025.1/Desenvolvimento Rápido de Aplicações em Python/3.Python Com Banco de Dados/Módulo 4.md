# **Recuperação de registros em tabelas do banco de dados**

## 1. Seleção de registros de uma tabela

Selecionar registros em um banco de dados é essencial para obter informações relevantes. ==O comando `SQL SELECT` é utilizado para realizar essas consultas, podendo incluir filtros e manipulações para facilitar o trabalho com os dados.==

### Sintaxe Básica do Comando SELECT

```sql
SELECT colunas FROM tabela WHERE condição;
```

- **`colunas`**: Especifica as colunas que você deseja recuperar. ==Use `*` para selecionar todas as colunas.==
- **`tabela`**: O nome da tabela de onde os dados serão selecionados.
- **`condição` (opcional)**: Filtra os registros retornados.

### Exemplo 1: Recuperando Todos os Registros

#### *SQL:*

```sql
SELECT Nome, Oculos FROM Pessoa;
```

#### *Python:*

```python
import sqlite3

# Conectar ao banco de dados
conexao = sqlite3.connect("meu_banco.db")
cursor = conexao.cursor()

# Executar consulta
cursor.execute("SELECT Nome, Oculos FROM Pessoa;")
registros = cursor.fetchall()

# Imprimir resultados
for registro in registros:
    print(f"Nome: {registro[0]}, Óculos: {registro[1]}")

# Fechar conexão
cursor.close()
conexao.close()
```

#### *Resultado:*

```plaintext
Nome: Maria, Óculos: 0
Nome: João, Óculos: 1
Nome: Silva, Óculos: 1
```

### Exemplo 2: Utilizando Filtros com WHERE

#### *Objetivo: Retornar apenas pessoas que usam óculos.*

#### *SQL:*

```sql
SELECT * FROM Pessoa WHERE Oculos = 1;
```

#### *Python:*

```python
# Definir consulta SQL com filtro
cursor.execute("SELECT * FROM Pessoa WHERE Oculos = ?;", (1,))
pessoas_com_oculos = cursor.fetchall()

# Imprimir resultados
for pessoa in pessoas_com_oculos:
    print(f"CPF: {pessoa[0]}, Nome: {pessoa[1]}, Nascimento: {pessoa[2]}, Óculos: {pessoa[3]}")
```

#### *Resultado:*

```plaintext
CPF: 12345678900, Nome: João, Nascimento: 2000-01-31, Óculos: 1
CPF: 30000000099, Nome: Silva, Nascimento: 1990-03-30, Óculos: 1
```

### Trabalhando com Conversão de Tipos (Datas e Booleanos)

#### *Motivação: Convertendo tipos como `BOOLEAN` e `DATE` para os tipos Python correspondentes.*

1. **Ajuste na Conexão**: Use o argumento `PARSE_DECLTYPES` na função `sqlite3.connect`:
    
    ```python
    conexao = sqlite3.connect("meu_banco.db", detect_types=sqlite3.PARSE_DECLTYPES)
    ```
    
2. **Configurar Conversor**: Adicione conversores personalizados para tipos não nativamente suportados, como `BOOLEAN`:
    
    ```python
    def conv_bool(valor):
        return True if valor == 1 else False
    
    sqlite3.register_converter("BOOLEAN", conv_bool)
    ```
    
3. **Script Completo para Conversões**
    
    ```python
    conexao = sqlite3.connect("meu_banco.db", detect_types=sqlite3.PARSE_DECLTYPES)
    cursor = conexao.cursor()
    
    # Consulta
    cursor.execute("SELECT * FROM Pessoa WHERE Oculos = ?", (1,))
    pessoas = cursor.fetchall()
    
    for pessoa in pessoas:
        print(f"CPF: {pessoa[0]}, Nome: {pessoa[1]}, Nascimento: {pessoa[2]}, Óculos: {pessoa[3]}")
    
    cursor.close()
    conexao.close()
    ```
    

#### *Saída Esperada:*

- Datas formatadas como `datetime.date`.
- Atributos booleanos representados como `True` ou `False`.

### Conclusão

==O comando `SELECT` é extremamente versátil, permitindo não só a recuperação de dados, mas também a aplicação de filtros e manipulações.== A integração com Python facilita a exibição e o processamento desses registros.

---
## 2. Seleção de registros utilizando junção e de registros relacionados

==Ao usar o comando `JOIN` em SQL, podemos combinar dados de múltiplas tabelas, formando uma visão completa sobre os relacionamentos entre entidades.== Esse método permite, por exemplo, listar veículos com suas respectivas marcas ou mostrar todas as pessoas com seus veículos e marcas.

### Seleção de Registros Utilizando Junção

#### *Sintaxe do Comando JOIN*

```sql
SELECT tabela1.coluna1, tabela2.coluna2
FROM tabela1
JOIN tabela2
ON tabela1.colunaX = tabela2.colunaY;
```

- **`tabela1.colunaX` e `tabela2.colunaY`**: Atributos usados para alinhar os registros.

#### *Exemplo 1: Veículos com suas Marcas*

Desejamos substituir o ID da marca por seu nome ao listar veículos.

- **SQL**:

```sql
SELECT Veiculo.Placa, Marca.Nome
FROM Veiculo
JOIN Marca
ON Veiculo.Marca = Marca.Id;
```

- **Python**:

```python
import sqlite3

# Conectar ao banco de dados
conexao = sqlite3.connect("meu_banco.db")
cursor = conexao.cursor()

# Executar consulta com junção
cursor.execute("""
    SELECT Veiculo.Placa, Marca.Nome
    FROM Veiculo
    JOIN Marca
    ON Veiculo.Marca = Marca.Id;
""")

# Recuperar resultados
registros = cursor.fetchall()

# Imprimir resultados
for registro in registros:
    print(f"Placa: {registro[0]} , Marca: {registro[1]}")

# Fechar conexão
cursor.close()
conexao.close()
```

#### *Exemplo 2: Veículos com Objetos de Marca*

Para criar um objeto da classe `Marca` relacionado a cada veículo:

- **Python**:

```python
# Criar comando SQL com junção
cursor.execute("""
    SELECT Veiculo.*, Marca.*
    FROM Veiculo
    JOIN Marca
    ON Veiculo.Marca = Marca.Id;
""")

# Recuperar registros
registros = cursor.fetchall()

for registro in registros:
    # Criar objeto Marca
    marca = Marca(*registro[6:9])
    
    # Criar objeto Veiculo com referência à Marca
    veiculo = Veiculo(*registro[:5], marca)
    
    print(f"Placa: {veiculo.Placa}, Marca: {veiculo.Marca.Nome}")
```

>*Nesse exemplo, usamos **array slicing** para dividir os atributos de cada tabela.*

### Seleção de Registros Relacionados

#### *Objetivo: Mostrar todas as pessoas cadastradas com seus veículos e marcas.*

**Estratégia**:

1. Criar uma função que retorna os veículos de uma pessoa.
2. Utilizar essa função em um script principal para listar pessoas e seus veículos.

#### *Função para Recuperar Veículos*

```python
def recuperar_veiculos(conexao, cpf):
    cursor = conexao.cursor()
    cursor.execute("""
        SELECT Veiculo.Placa, Marca.Nome
        FROM Veiculo
        JOIN Marca
        ON Veiculo.Marca = Marca.Id
        WHERE Veiculo.Proprietario = ?;
    """, (cpf,))
    
    veiculos = []
    for registro in cursor.fetchall():
        veiculos.append(Veiculo(registro[0], registro[1]))
    cursor.close()
    return veiculos
```

#### *Script Principal*

```python
conexao = sqlite3.connect("meu_banco.db")
cursor = conexao.cursor()

# Recuperar pessoas
cursor.execute("SELECT * FROM Pessoa;")
pessoas_registradas = cursor.fetchall()

# Processar pessoas e seus veículos
for pessoa in pessoas_registradas:
    pessoa_obj = Pessoa(*pessoa)
    pessoa_obj.veiculos = recuperar_veiculos(conexao, pessoa[0])
    print(pessoa_obj.Nome)
    for veiculo in pessoa_obj.veiculos:
        print(f"{veiculo.Placa} {veiculo.Marca}")

cursor.close()
conexao.close()
```

### *Resultado Final*

A saída será uma lista de pessoas, seguida por seus veículos e respectivas marcas:

```plaintext
Maria
AAA0001 Marca A
BAA0002 Marca A

José
CAA0003 Marca B

Silva
DAA0004 Marca B
```

>*A ordem dos elementos em uma cláusula **JOIN** não afeta o resultado final da consulta.*