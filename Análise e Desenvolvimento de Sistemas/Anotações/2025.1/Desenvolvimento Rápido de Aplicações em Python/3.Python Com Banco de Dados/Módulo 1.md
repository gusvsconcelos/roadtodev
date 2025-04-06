# **Frameworks e bibliotecas para gerenciamento de dados**

## 1. Conectores para banco de dados

==Conectores para bancos de dados são bibliotecas essenciais em Python para integrar aplicações com diferentes *SGBDs*== (Sistemas de Gerenciamento de Bancos de Dados).

==Eles garantem uma comunicação eficiente, segura e seguem a especificação **PEP 249 (DB-API 2.0)**, que estabelece padrões como:==

- **Nomes de métodos**: `close`, `commit`, `cursor`.
- **Nomes de classes**: `Connection`, `Cursor`.
- **Tipos de exceção**: `IntegrityError`, `InternalError`.

Esses padrões asseguram consistência e portabilidade entre diferentes bancos.

### Principais Conectores

#### *PostgreSQL*

- **Psycopg2**: Conector mais utilizado para PostgreSQL, com suporte a recursos avançados e alta eficiência.

#### *MySQL*

- **mysqlclient**: Desempenho eficiente, mas depende de pacotes nativos.
- **PyMySQL**: Fácil de instalar, embora menos performático.
- **MySQL Connector/Python**: Combina facilidade de uso e suporte oficial.

#### **SQLite**

- **sqlite3**: Adaptador padrão do Python, ideal para bancos locais e pequenas aplicações.

### Por Que Usar Conectores?

- **Criação de conexões**: Estabelecem comunicação com o banco de dados.
- **Execução de operações CRUD**: Simplificam tarefas como inserir, atualizar, deletar e consultar dados.
- **Compatibilidade**: Adotam interfaces padronizadas, reduzindo esforço ao mudar de SGBD.

### Escolhendo o Conector Adequado

**Ao selecionar um conector, considere**:

- **Compatibilidade** com o banco de dados.
- **Facilidade de instalação e uso**.
- **Desempenho** em operações específicas.
- **Recursos oferecidos**, como suporte a transações ou recursos exclusivos do banco.

>*Conectores são cruciais para projetos que necessitam de integração com bancos de dados, sejam locais (SQLite) ou remotos (PostgreSQL, MySQL).*

---
## 2. Principais métodos e exceções dos conectores em Python

==Conectores fornecem métodos para interagir com bancos de dados e também lançam exceções que ajudam a identificar e tratar erros durante as operações.==

### Principais Métodos dos Conectores

==Os conectores seguem um fluxo básico de trabalho, aplicável a qualquer integração com bancos de dados:==

- **Conectar**: Criar uma conexão com o banco usando o método `connect()`.
- **Executar**: Utilizar o método `execute()` para enviar comandos SQL.
- **Enviar comandos**: Comando SQL é processado no banco.
- **Confirmar**: Salvar as alterações usando `commit()`.
- **Fechar**: Encerrar a conexão com o banco.

#### *Exemplo com SQLite*

```python
import sqlite3 as conector

# Criando conexão e cursor
conexao = conector.connect("meu_banco.db")
cursor = conexao.cursor()

# Executando comandos SQL
cursor.execute("CREATE TABLE IF NOT EXISTS exemplo (id INTEGER PRIMARY KEY, nome TEXT)")
cursor.execute("INSERT INTO exemplo (nome) VALUES ('Python')")

# Confirmando alterações
conexao.commit()

# Fechando conexão
cursor.close()
conexao.close()
```

>*Esse fluxo de trabalho é replicado para outros conectores, como `mysql.connector` e `psycopg2`, bastando alterar o módulo importado.*

### Principais Exceções dos Conectores

**A DB-API 2.0 especifica algumas exceções que podem ser lançadas pelos conectores**:

- **Error**: Exceção base para todas as outras.
- **IntegrityError**: Violação de integridade, como duplicação de chave primária.
- **OperationalError**: Problemas operacionais, como falha de conexão.
- **DatabaseError**: Erros gerais relacionados ao banco de dados.
- **ProgrammingError**: Comandos SQL inválidos ou sintaxes incorretas.
- **NotSupportedError**: Função ou operação não suportada pelo banco.

#### *Exemplo de Tratamento de Exceções*

```python
try:
    conexao = conector.connect("meu_banco.db")
    cursor = conexao.cursor()
    cursor.execute("INSERT INTO exemplo (id, nome) VALUES (1, 'Python')")
    conexao.commit()
except conector.IntegrityError:
    print("Erro: Chave primária duplicada!")
except conector.OperationalError as erro:
    print(f"Erro operacional: {erro}")
finally:
    if conexao:
        conexao.close()
```

### Flexibilidade e Portabilidade

**Uma das vantagens dos conectores que seguem a DB-API 2.0 é a padronização. Isso permite**:

- **Troca de banco de dados sem grandes alterações no código**: Alterar apenas o módulo importado.
- **Compatibilidade com diferentes SGBDs**: Seguindo o mesmo fluxo básico.

==Apesar disso, conectores oferecem funcionalidades específicas para seus bancos.==

- **Exemplo**: `bulk inserts` no MySQL, suporte avançado a transações no PostgreSQL.

---
## 3. Tipos de dados

==A escolha correta dos tipos de dados em um banco de dados é essencial para melhorar o desempenho, garantir a integridade dos dados e otimizar o armazenamento.==

Além disso, cada SGBD pode ter particularidades nos tipos suportados, sendo crucial consultar sua documentação.

### Principais Tipos de Dados

**Os tipos mais comuns incluem**:

- **INTEGER**: Números inteiros.
- **REAL**: Números de ponto flutuante.
- **TEXT**: Dados alfanuméricos.
- **BLOB**: Dados binários, como imagens ou arquivos.
- **NULL**: Representa valores nulos.

### O Caso do SQLite

O SQLite opera com uma abordagem distinta, usando **classes de armazenamento** e **afinidades de tipo**:

1. **Classes de armazenamento**:

    - **NULL**: Valores nulos.
    - **INTEGER**: Números inteiros.
    - **REAL**: Números de ponto flutuante.
    - **TEXT**: Dados alfanuméricos.
    - **BLOB**: Dados armazenados exatamente como foram fornecidos.
		
1. **Afinidades de tipo**:

    - ==Permitem armazenar diferentes tipos de dados em uma mesma coluna.==
    - **As afinidades suportadas são**:
		
        - **TEXT**: Para dados de texto, como VARCHAR, CLOB.
        - **NUMERIC**: Para números com possibilidade de precisão, como DECIMAL, BOOLEAN, DATE.
        - **INTEGER**: Para números inteiros.
        - **REAL**: Para números de ponto flutuante.
        - **NONE**: Sem tipo específico.

### Mapeamento e Afinidades no SQLite

==O SQLite converte tipos não suportados para aqueles que reconhece, usando afinidades.==

**Exemplos**:

- Tipos como `VARCHAR`, `CHARACTER`, ou `NVARCHAR` são convertidos para **TEXT**.
- Tipos como `DECIMAL` ou `BOOLEAN` são convertidos para **NUMERIC**.
- Tipos como `DOUBLE` e `FLOAT` são convertidos para **REAL**.
- Tipos como `BLOB` permanecem inalterados.

#### *Tabela de Afinidades no SQLite:*

| **Tipo no CREATE TABLE**       | **Afinidade** |
| ------------------------------ | ------------- |
| INT, INTEGER, TINYINT, BIGINT  | INTEGER       |
| CHARACTER, VARCHAR, TEXT, CLOB | TEXT          |
| BLOB                           | BLOB          |
| REAL, DOUBLE, FLOAT            | REAL          |
| NUMERIC, DECIMAL, BOOLEAN      | NUMERIC       |

### Importância em Ambientes de Desenvolvimento e Produção

==Mesmo ao usar o SQLite em desenvolvimento, é possível mapear tipos para garantir compatibilidade com bancos de produção (como MySQL ou PostgreSQL). Esse cuidado permite projetar tabelas que funcionarão de maneira consistente em diferentes ambientes.==