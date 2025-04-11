# **Inserção, remoção e atualização de tabelas do banco de dados**

## 1. Inserção de Dados em Tabelas

A inserção de dados em tabelas é uma operação essencial para expandir e manter um banco de dados atualizado.

==O comando `INSERT INTO` permite adicionar registros de maneira eficiente, garantindo que as informações necessárias sejam armazenadas corretamente.==

### Exemplo de Inserção

Vamos inserir o seguinte registro na tabela `Pessoa`:

- **CPF**: `12345678900`
- **Nome**: `João`
- **Nascimento**: `31/01/2000`
- **Óculos**: `Sim (True)`

#### *Comando SQL*

```sql
INSERT INTO Pessoa (CPF, Nome, Nascimento, Oculos)
VALUES (12345678900, 'João', '2000-01-31', 1);
```

- A data `31/01/2000` foi convertida para o formato `2000-01-31`, utilizado por bancos como MySQL e PostgreSQL. No SQLite, ela será convertida para TEXT por afinidade.
- O valor `1` representa o booleano `True`, já que o tipo BOOLEAN é convertido para INTEGER no SQLite.

### Script Python para Inserção

Aqui está o código Python para inserir os dados na tabela `Pessoa`:

```python
import sqlite3

# Conectar ao banco de dados
conexao = sqlite3.connect("meu_banco.db")
cursor = conexao.cursor()

# Comando SQL para inserção
comando = """
INSERT INTO Pessoa (CPF, Nome, Nascimento, Oculos)
VALUES (12345678900, 'João', '2000-01-31', 1);
"""

# Executar o comando e confirmar alterações
cursor.execute(comando)
conexao.commit()

# Fechar cursor e conexão
cursor.close()
conexao.close()

print("Dados inseridos com sucesso!")
```

### Explicação

- **Conexão com o banco**: O código conecta-se ao arquivo `meu_banco.db` ou o cria se não existir.
- **Comando SQL**: Insere os dados definidos.
- **Execução e confirmação**: Comando executado com `execute()` e mudanças salvas com `commit()`.
- **Finalização**: Fecha o cursor e a conexão.

### Verificação

Após executar o script, você pode visualizar o registro no banco de dados usando ferramentas como **DB Browser for SQLite**.

---
## 2. Inserção de dados em tabela com queries dinâmicas

A utilização de queries dinâmicas com delimitadores é uma prática indispensável para tornar o código mais flexível e seguro, além de otimizar a inserção repetitiva de registros em bancos de dados.

==Essa técnica evita brechas de **SQL Injection** e automatiza a manipulação de dados de forma eficiente.==

### Delimitadores

==Os delimitadores são utilizados para indicar que determinados valores serão substituídos na query SQL antes da execução.== Entre os principais estão:

- **`?`**: Utilizado no SQLite.
- **`%s`**: Utilizado no PostgreSQL (psycopg2) e MySQL (PyMySQL).

==Esses delimitadores garantem que os valores sejam formatados corretamente para o banco de dados, como aspas para textos e números sem aspas.==

### Exemplo com SQLite

#### *1. Definindo a Classe Pessoa*

Para ilustrar, criamos uma classe `Pessoa` que modela a entidade do banco de dados:

```python
class Pessoa:
    def __init__(self, cpf, nome, nascimento, oculos):
        self.cpf = cpf
        self.nome = nome
        self.nascimento = nascimento
        self.oculos = oculos
```

#### *2. Inserindo Dados Dinamicamente*

A query dinâmica é criada utilizando delimitadores (`?`) e executada com os valores correspondentes:

```python
import sqlite3

# Conectar ao banco de dados
conexao = sqlite3.connect("meu_banco.db")
cursor = conexao.cursor()

# Criar objeto da classe Pessoa
nova_pessoa = Pessoa(10000000099, 'Maria', '1990-01-31', False)

# Query dinâmica com delimitadores
comando_sql = """
INSERT INTO Pessoa (CPF, Nome, Nascimento, Oculos)
VALUES (?, ?, ?, ?);
"""

# Executar query dinâmica com uma tupla de parâmetros
cursor.execute(comando_sql, (nova_pessoa.cpf, nova_pessoa.nome, nova_pessoa.nascimento, nova_pessoa.oculos))

# Confirmar alterações e fechar conexão
conexao.commit()
cursor.close()
conexao.close()
print("Dados inseridos com sucesso!")
```

### Como Funciona?

- **Delimitadores na query**: Representam os valores que serão substituídos dinamicamente.
- **Tupla de parâmetros**: Os valores são fornecidos em uma tupla ou lista, na mesma ordem dos delimitadores.
- **Segurança**: Os conectores concatenam os parâmetros à query SQL, escapando caracteres especiais automaticamente, prevenindo vulnerabilidades.

### Flexibilidade

- Permite reutilizar a mesma query SQL para múltiplos registros.
- Melhora a manutenção do código e reduz redundâncias.
- Garante compatibilidade com diferentes conectores (verifique o delimitador correto em cada biblioteca).

---
## 3. Inserção de Dados com Queries Dinâmicas e Argumentos Nomeados

A utilização de argumentos nomeados é uma abordagem clara, segura e flexível para a inserção de dados em tabelas de bancos de dados.

==Essa prática organiza o código, reduz erros e facilita a manutenção, especialmente em sistemas com atributos complexos.==

### Por que Usar Argumentos Nomeados?

- **Flexibilidade**: Não há necessidade de manter a ordem dos valores.
- **Clareza**: Cada valor é associado ao nome do campo correspondente.
- **Segurança**: ==Protege contra **SQL Injection** ao permitir que o conector processe os valores adequadamente.==

### Exemplo com SQLite

#### *1. Criando a Classe Pessoa*

A classe representa a tabela `Pessoa` no banco:

```python
class Pessoa:
    def __init__(self, cpf, nome, nascimento, oculos):
        self.cpf = cpf
        self.nome = nome
        self.nascimento = nascimento
        self.oculos = oculos
```

#### *2. Inserindo Dados com Argumentos Nomeados*

Aqui está um exemplo prático de como usar argumentos nomeados com o SQLite:

```python
import sqlite3

# Conectar ao banco de dados
conexao = sqlite3.connect("meu_banco.db")
cursor = conexao.cursor()

# Criar objeto do tipo Pessoa
pessoa = Pessoa(20000000099, 'José', '1990-02-28', False)

# Query dinâmica com argumentos nomeados
comando_sql = """
INSERT INTO Pessoa (CPF, Nome, Nascimento, Oculos)
VALUES (:cpf, :nome, :nascimento, :oculos);
"""

# Executar comando utilizando um dicionário
cursor.execute(comando_sql, {
    'cpf': pessoa.cpf,
    'nome': pessoa.nome,
    'nascimento': pessoa.nascimento,
    'oculos': pessoa.oculos
})

# Confirmar alterações e fechar a conexão
conexao.commit()
cursor.close()
conexao.close()
print("Registro inserido com sucesso!")
```

### Simplificando o Código com `vars()`

Para reduzir a complexidade, especialmente com muitos atributos, podemos usar a função `vars()`, que converte objetos em dicionários:

```python
# Criar comando SQL sem listar colunas (todos os atributos serão inseridos)
comando_sql = "INSERT INTO Pessoa VALUES (:cpf, :nome, :nascimento, :oculos);"

# Executar comando com vars()
cursor.execute(comando_sql, vars(pessoa))
```

==O uso de `vars()` elimina a necessidade de criar manualmente um dicionário, tornando o código mais enxuto.==

### Atenção: Restrições de Chaves Estrangeiras

==Quando inserimos registros que referenciam outras tabelas, as chaves associadas (como `proprietario` e `marca` em tabelas relacionadas) devem existir no banco. Caso contrário, um **IntegrityError** será lançado com a mensagem “Falha na restrição de chave estrangeira”.==

### Ampliando para Outras Tabelas

Você pode utilizar essa lógica para inserir registros em tabelas relacionadas:

1. **Habilite verificações de chaves estrangeiras com o comando PRAGMA**:

```python
cursor.execute("PRAGMA foreign_keys = ON;")
```

2. **Insira registros na tabela `Marca` e use o `lastrowid`** para recuperar o ID da marca recém-inserida:

```python
marca = {'nome': 'Toyota', 'sigla': 'TY'}
cursor.execute("INSERT INTO Marca (Nome, Sigla) VALUES (:nome, :sigla);", marca)
marca_id = cursor.lastrowid
```

3. **Use o ID recuperado para inserir veículos relacionados**:

```python
veiculo = {'placa': 'XYZ1234', 'ano': 2020, 'cor': 'Vermelho', 'marca': marca_id, 'proprietario': 12345678900}
cursor.execute("""
INSERT INTO Veiculo (Placa, Ano, Cor, Marca, Proprietario)
VALUES (:placa, :ano, :cor, :marca, :proprietario);
""", veiculo)
```

### Conclusão

==Usar argumentos nomeados e funções como `vars()` otimiza o desenvolvimento, especialmente ao trabalhar com tabelas relacionadas e atributos complexos. Essa prática mantém o código legível, flexível e seguro.==

---
## 4. Atualização e Remoção de Dados em Tabelas

Manter a relevância dos dados em um banco de dados é essencial para a integridade da aplicação.

==Com os comandos `SQL UPDATE` e `SQL DELETE`, podemos atualizar ou remover registros de forma eficiente, mantendo o banco sempre consistente.==

### Atualização de Dados em Tabelas

Para modificar registros, utilizamos o comando `SQL UPDATE`. Sua sintaxe básica é:

```sql
UPDATE tabela SET coluna1 = valor1, coluna2 = valor2 WHERE condição;
```

- **Sem cláusula `WHERE`: Atualiza todos os registros da tabela.
- **Com delimitadores `?` ou argumentos nomeados**: Torna a query dinâmica e segura.

#### *Exemplo com SQLite*

- **Sem delimitadores**:

```sql
UPDATE Pessoa SET Oculos = 1;
```

Atualiza o valor para `1 (True)` em **todos os registros**, pois a cláusula `WHERE` foi omitida.

- **Com delimitadores**:

```sql
UPDATE Pessoa SET Oculos = ? WHERE CPF = ?;
```

Atualiza o atributo `Oculos` para `0 (False)` somente para o registro com CPF `30000000099`.

- **Com argumentos nomeados**:

```sql
UPDATE Pessoa SET Oculos = :oculos WHERE CPF = :cpf;
```

Atualiza `Oculos` para `0 (False)` no registro cujo CPF é `20000000099`.

#### *Implementação em Python*

```python
import sqlite3

# Conectar ao banco
conexao = sqlite3.connect("meu_banco.db")
cursor = conexao.cursor()

# Habilitar checagem de chave estrangeira
cursor.execute("PRAGMA foreign_keys = ON;")

# Sem delimitadores
cursor.execute("UPDATE Pessoa SET Oculos = 1;")

# Com delimitadores "?"
cursor.execute("UPDATE Pessoa SET Oculos = ? WHERE CPF = ?;", (0, 30000000099))

# Com argumentos nomeados
cursor.execute("UPDATE Pessoa SET Oculos = :oculos WHERE CPF = :cpf;", {'oculos': 0, 'cpf': 20000000099})

# Confirmar e fechar conexão
conexao.commit()
cursor.close()
conexao.close()
```

### Cuidados com o Comando UPDATE

- **Cláusula `WHERE`**: Sempre use para evitar alterações massivas acidentais.
- **Referências em outras tabelas**: ==Atualizar chaves primárias pode gerar erros de **IntegrityError**.==

### Remoção de Dados em Tabelas

Para excluir registros, utilizamos o comando `SQL DELETE`. Sua sintaxe básica é:

```sql
DELETE FROM tabela WHERE condição;
```

- **Sem cláusula `WHERE`**: Remove todos os registros da tabela.
- **Com delimitadores**: Dinamiza a query e garante segurança.

#### *Exemplo com SQLite*

- **Sem delimitadores**:

```sql
DELETE FROM Pessoa WHERE CPF = 12345678900;
```

Remove o registro cujo CPF seja `12345678900`.

- **Com argumentos nomeados**:

```sql
DELETE FROM Pessoa WHERE CPF = :cpf;
```

Remove o registro com CPF definido no argumento nomeado.

#### *Implementação em Python*

```python
# Conectar ao banco
conexao = sqlite3.connect("meu_banco.db")
cursor = conexao.cursor()

# Habilitar checagem de chave estrangeira
cursor.execute("PRAGMA foreign_keys = ON;")

# Remoção direta
cursor.execute("DELETE FROM Pessoa WHERE CPF = 12345678900;")

# Remoção com argumentos nomeados
cursor.execute("DELETE FROM Pessoa WHERE CPF = :cpf;", {'cpf': 20000000099})

# Confirmar e fechar conexão
conexao.commit()
cursor.close()
conexao.close()
```

### Cuidados com o Comando DELETE

- ==**Referências**: Certifique-se de que o registro a ser excluído não esteja relacionado por chaves estrangeiras. Caso contrário, uma exceção **IntegrityError** será lançada.==
- **Cláusula `WHERE`**: Evite omitir para prevenir exclusões desnecessárias.