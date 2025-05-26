## ✅ RESUMO PARA PROVAS – CRIAÇÃO E MANIPULAÇÃO DE OBJETOS NO POSTGRESQL

---

### 🔹 INTRODUÇÃO E INSTALAÇÃO DO POSTGRESQL

- **PostgreSQL**: SGBD relacional de código aberto, multiplataforma.
    
- **Histórico**:
    
    - Surgiu do projeto POSTGRES (sucessor do INGRES - UC Berkeley).
        
    - Tornou-se PostgreSQL em 1996, com SQL como linguagem padrão.
        
- **Modelo cliente-servidor**:
    
    - Cliente envia comandos SQL.
        
    - Servidor gerencia execução, arquivos e conexões (via TCP/IP).
        

#### Instalação:

- **Linux**:
    
    - Descompactar código-fonte: `gunzip`, `tar xf`
        
    - Compilar e instalar: `./configure`, `gmake`, `gmake install`
        
    - Configuração: criar usuário postgres, diretório data, iniciar servidor
        
- **Windows**:
    
    - Instalador gráfico com pgAdmin, psql e Stack Builder.
        
    - Diretório padrão: `C:\Program Files\PostgreSQL\12`
        

---

### 🔹 CRIAÇÃO DE DATABASES E TABELAS

#### Criando databases

- **CREATE DATABASE NOME;**
    
- Interface gráfica (pgAdmin) ou linha de comando (psql)
    
- Schema padrão: **public**
    

#### Criando schemas

- **CREATE SCHEMA nome_schema;**
    
- Especificar schema: `nome_schema.nome_tabela`
    

#### Criando tabelas

```sql
CREATE TABLE nome_tabela (
  coluna1 tipo [restrição],
  ...,
  PRIMARY KEY (coluna),
  FOREIGN KEY (coluna) REFERENCES outra_tabela(coluna)
);
```

#### Tipos de dados comuns:

- **int, serial, bigint, smallint**
    
- **char(n), varchar(n), text**
    
- **date, time, timestamp**
    
- **decimal, numeric, real, double**
    
- **money**
    

#### Restrições:

- **NOT NULL**: valor obrigatório
    
- **UNIQUE**: valores únicos
    
- **PRIMARY KEY**: identificação única
    
- **FOREIGN KEY**: integridade referencial
    
- **CHECK**: condicional (ex: CHECK (idade >= 18))
    

---

### 🔹 ALTERAÇÃO E REMOÇÃO DE TABELAS

#### ALTER TABLE:

- Adicionar coluna: `ALTER TABLE nome ADD nova_coluna tipo;`
    
- Remover coluna: `ALTER TABLE nome DROP coluna;`
    
- Adicionar FK: `ALTER TABLE nome ADD FOREIGN KEY (...);`
    
- Atualizar FK com CASCADE:
    

```sql
ALTER TABLE nome
  DROP CONSTRAINT nome_fk,
  ADD CONSTRAINT nome_fk FOREIGN KEY (...) REFERENCES ... ON UPDATE CASCADE;
```

#### DROP TABLE:

- `DROP TABLE nome;`
    
- Se houver FK, usar: `DROP TABLE nome CASCADE;`
    

---

### 🔹 MANIPULAÇÃO DE LINHAS (DML)

#### Comandos CRUD:

- **INSERT**: inserir registros
    

```sql
INSERT INTO tabela (col1, col2) VALUES (val1, val2);
```

- **SELECT**: consultar dados
    
- **UPDATE**: atualizar registros
    

```sql
UPDATE tabela SET col=valor WHERE condição;
```

- **DELETE**: excluir registros
    

```sql
DELETE FROM tabela WHERE condição;
```

#### Cuidados:

- **PK**: valores devem ser únicos e não nulos
    
- **FK**: valores devem existir na tabela referenciada
    
- **ON DELETE CASCADE**: remove dependências automáticas
    

---

### 🔹 TRANSAÇÕES NO POSTGRESQL

#### Conceito:

- Conjunto de comandos executados como **unidade lógica**
    
- Garantias de **integridade** e **isolamento**
    

#### Comandos:

```sql
BEGIN; -- Início da transação
COMMIT; -- Confirma a transação
ROLLBACK; -- Desfaz a transação
SAVEPOINT nome; -- Ponto de retorno
ROLLBACK TO nome; -- Retorna ao ponto
```

#### Tipos:

- **READ ONLY**: apenas leitura
    
- **READ WRITE**: padrão, permite alterações
    

```sql
SET TRANSACTION READ ONLY;
```

#### Propriedades ACID:

- **Atomicidade**: tudo ou nada
    
- **Consistência**: mantém regras do BD
    
- **Isolamento**: transações não se afetam
    
- **Durabilidade**: alterações persistem após sucesso
    

#### Problemas evitados:

- Atualização perdida
    
- Atualização temporária
    
- Leitura não repetitiva
    
- Resumo incorreto
    

---

### 🖊️ QUESTÕES COMENTADAS – OBJETOS NO POSTGRESQL

**1.** O comando abaixo realiza qual operação?

```sql
CREATE TABLE disciplina (
  codigo INT PRIMARY KEY,
  nome VARCHAR(80),
  carga INT
);
```

A) Cria um banco de dados  
B) Cria uma nova coluna  
C) Cria uma tabela com três colunas  
D) Cria uma view  
E) Atualiza registros existentes

✅ **Gabarito: C**

> O comando cria uma tabela com as colunas `codigo`, `nome` e `carga`, sendo `codigo` a chave primária.

---

**2.** Qual comando adiciona uma nova coluna à tabela `curso`?

A) ADD COLUMN curso nova_coluna VARCHAR(50);  
B) ALTER TABLE curso ADD nova_coluna VARCHAR(50);  
C) CREATE TABLE curso ADD COLUMN nova_coluna;  
D) ALTER DATABASE curso ADD nova_coluna;  
E) UPDATE TABLE curso ADD nova_coluna;

✅ **Gabarito: B**

> `ALTER TABLE` é o comando usado para alterar estruturas de tabelas já existentes.

---

**3.** Uma transação SQL começa com:

A) COMMIT  
B) INSERT  
C) BEGIN  
D) ROLLBACK  
E) SELECT

✅ **Gabarito: C**

> `BEGIN` é o comando que inicia uma transação no PostgreSQL.

---

**4.** Em relação ao tipo de dados `serial`:

A) Aceita apenas valores decimais  
B) Gera valor único e sequencial automaticamente  
C) Representa sequência de caracteres  
D) Define campo de texto longo  
E) Indica campo obrigatoriamente nulo

✅ **Gabarito: B**

> `serial` é usado para gerar automaticamente valores únicos e sequenciais, comumente usado como PK.

---

**5.** Qual comando desfaz todas as operações de uma transação?

A) COMMIT  
B) SAVEPOINT  
C) UPDATE  
D) DELETE  
E) ROLLBACK

✅ **Gabarito: E**

> `ROLLBACK` desfaz as alterações feitas durante a transação, restaurando o estado anterior.