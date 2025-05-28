## ✅ RESUMO PARA PROVAS – CONSULTAS EM UMA TABELA NO POSTGRESQL

---
### ESTRUTURA BÁSICA DO SELECT

#### Sintaxe simples

```sql
SELECT coluna1, coluna2, ... FROM tabela;
```

- `SELECT *` retorna todas as colunas.
- `AS` permite apelidar colunas: `SELECT nome AS "Nome Completo"`

#### Exemplo:

```sql
SELECT CODIGOALUNO AS "Matrícula", NOME AS "Nome", DTNASCIMENTO AS "Nascimento"
FROM ALUNO;
```

---
### FUNÇÕES DE DATA E HORA

- `CURRENT_DATE`, `CURRENT_TIME`, `CURRENT_TIMESTAMP`
- `EXTRACT(parte FROM data)` extrai partes como `YEAR`, `MONTH`, `DAY`, `DOW`, `DOY`, `CENTURY`
- `AGE(data)` calcula a idade
- `CASE WHEN` define condições (usado para exibir dia da semana, faixa etária etc.)

#### Exemplo:

```sql
SELECT NOME, AGE(DTNASCIMENTO) AS "Idade", EXTRACT(YEAR FROM AGE(DTNASCIMENTO)) AS "Idade Anos"
FROM ALUNO;
```

---
### FUNÇÕES DE AGREGAÇÃO

| Função          | Finalidade      |
| --------------- | --------------- |
| `COUNT(*)`      | Conta registros |
| `MIN(col)`      | Valor mínimo    |
| `MAX(col)`      | Valor máximo    |
| `SUM(col)`      | Soma valores    |
| `AVG(col)`      | Média           |
| `STDDEV(col)`   | Desvio padrão   |
| `VARIANCE(col)` | Variância       |

#### Exemplo:

```sql
SELECT COUNT(*) AS "Alunos", MIN(EXTRACT(YEAR FROM AGE(DTNASCIMENTO))) AS "Menor idade"
FROM ALUNO;
```

---
### CRIAÇÃO DE TABELA E VIEW VIA SELECT

#### Criar tabela:

```sql
CREATE TABLE nova_tabela AS SELECT ... FROM ...;
```

#### Criar view:

```sql
CREATE VIEW nome_view AS SELECT ... FROM ...;
```

- Views facilitam a reutilização de consultas complexas.

---
### CLAUSULAS WHERE E ORDER BY

#### WHERE

- Filtra registros com base em condições

```sql
SELECT * FROM ALUNO WHERE SEXO = 'F';
```

- Operadores:
    
    - Relacionais: `<`, `<=`, `=`, `>=`, `>`, `<>`
    - Lógicos: `AND`, `OR`, `NOT`

#### ORDER BY

- Ordena resultados (ascendente é padrão)
    
```sql
SELECT * FROM ALUNO ORDER BY NOME;
SELECT * FROM ALUNO ORDER BY EXTRACT(MONTH FROM DTNASCIMENTO), NOME;
```

---
### FILTRAGEM AVANÇADA

#### IN

```sql
WHERE coluna IN (valor1, valor2, ...)
```

#### BETWEEN

```sql
WHERE coluna BETWEEN valor1 AND valor2
```

#### LIKE (busca textual)

```sql
WHERE nome LIKE '%Silva%'; -- qualquer lugar
WHERE nome LIKE '_a%'; -- segunda letra a
WHERE nome NOT LIKE '%Maria%'; -- ignora Maria
```

#### IS NULL / IS NOT NULL

```sql
WHERE EMAIL IS NULL;
```

### AGRUPAMENTO DE DADOS

#### GROUP BY

- Agrupa registros para aplicar funções de agregacão

```sql
SELECT SEXO, COUNT(*) AS QUANTIDADE
FROM FUNCIONARIO
GROUP BY SEXO;
```

#### HAVING

- Filtra grupos criados pelo `GROUP BY`

```sql
SELECT EXTRACT(MONTH FROM DTNASCIMENTO) AS MES, COUNT(*)
FROM FUNCIONARIO
GROUP BY MES
HAVING COUNT(*) > 1;
```

---
### 🖊️ QUESTÕES COMENTADAS

**1.** Qual comando exibe nome e idade dos alunos?

A) SELECT * FROM ALUNO  
==B) SELECT NOME, AGE(DTNASCIMENTO) FROM ALUNO==  
C) SELECT NOME, DTNASCIMENTO FROM ALUNO  
D) SELECT NOME FROM ALUNO WHERE IDADE > 20  
E) SELECT AGE(DTNASCIMENTO) FROM ALUNO

✅ **Gabarito: B**

> A função AGE retorna a idade baseada na data atual.

---

**2.** Qual comando conta os alunos com email do Gmail?

A) SELECT * FROM ALUNO WHERE EMAIL = 'gmail'  
==B) SELECT COUNT(*) FROM ALUNO WHERE EMAIL LIKE '%@GMAIL.%'==  
C) SELECT COUNT(EMAIL) FROM ALUNO WHERE EMAIL = '%gmail%'  
D) SELECT EMAIL FROM ALUNO WHERE EMAIL IS NOT NULL  
E) SELECT EMAIL LIKE '%GMAIL%' FROM ALUNO

✅ **Gabarito: B**

> Usa LIKE para localizar o padrão de email do Gmail e COUNT para contar.

---

**3.** Para retornar os autores de nacionalidade brasileira OU francesa:

A) WHERE NACIONALIDADE IN ('brasileira' AND 'francesa')  
B) WHERE NACIONALIDADE LIKE 'brasileira ou francesa'  
C) WHERE NACIONALIDADE = 'brasileira' OR 'francesa'  
==D) WHERE NACIONALIDADE IN ('brasileira', 'francesa')==  
E) WHERE NACIONALIDADE == ('brasileira', 'francesa')

✅ **Gabarito: D**

> O operador IN simplifica a busca por múltiplos valores.

---

**4.** Qual comando cria uma visão com nome e idade dos alunos?

A) CREATE TABLE VISTA AS SELECT ...  
B) CREATE INDEX ...  
==C) CREATE VIEW VISTA AS SELECT NOME, AGE(DTNASCIMENTO) FROM ALUNO;==  
D) CREATE DATABASE VIEW ...  
E) CREATE FUNCTION ...

✅ **Gabarito: C**

> A visão é criada com CREATE VIEW e encapsula uma consulta.

---

**5.** Para obter a média salarial por sexo, usa-se:

A) GROUP BY SEXO WITH AVG(SALARIO)  
B) SELECT AVG(SALARIO) GROUP SEXO  
C) SELECT AVG(SALARIO), SEXO FROM FUNCIONARIO  
==D) SELECT SEXO, AVG(SALARIO) FROM FUNCIONARIO GROUP BY SEXO==  
E) SELECT * FROM FUNCIONARIO WHERE SALARIO = AVG

✅ **Gabarito: D**

> Aplica função de agregação com agrupamento por sexo.