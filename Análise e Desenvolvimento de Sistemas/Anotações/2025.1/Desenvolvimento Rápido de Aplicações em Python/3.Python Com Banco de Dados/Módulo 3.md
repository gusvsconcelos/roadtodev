# **Inserção, remoção e atualização de tabelas do banco de dados**

## 1. Inserção de Dados em Tabelas

A inserção de dados em tabelas é uma operação essencial para expandir e manter um banco de dados atualizado. O comando `INSERT INTO` permite adicionar registros de maneira eficiente, garantindo que as informações necessárias sejam armazenadas corretamente.

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
## 2. 