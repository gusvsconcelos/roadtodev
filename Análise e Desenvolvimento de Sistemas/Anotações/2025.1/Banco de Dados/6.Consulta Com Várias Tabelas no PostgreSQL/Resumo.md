## ✅ RESUMO PARA PROVAS – CONSULTAS COM VÁRIAS TABELAS NO POSTGRESQL

---

### 🔹 1. JUNÇÕES ENTRE TABELAS

#### ⚖️ Produto cartesiano

- Combina todas as linhas de duas tabelas: `SELECT * FROM T1, T2;` ou `T1 CROSS JOIN T2`
    
- Gera muitos registros (|T1| x |T2|)
    
- Evitar quando não for necessário
    

#### ⚖️ INNER JOIN (junção interna)

- Retorna apenas registros com correspondência entre tabelas
    

```sql
SELECT * FROM T1 INNER JOIN T2 ON T1.chave = T2.chave;
```

- Alternativa com `USING`: `... USING(coluna)`
    

#### ⚖️ OUTER JOIN (junção externa)

- Inclui registros sem correspondência
    

|Tipo|Retorna...|
|---|---|
|LEFT|Todos da esquerda + correspondentes da direita|
|RIGHT|Todos da direita + correspondentes da esquerda|
|FULL|Todos de ambas, mesmo sem correspondência|

```sql
SELECT * FROM T1 LEFT JOIN T2 ON (...);
```

---

### 🔹 2. SUBCONSULTAS (ANINHADAS E CORRELATAS)

#### ☁️ Subconsulta aninhada

- Consulta interna é resolvida antes da externa
    

```sql
SELECT ... FROM T WHERE col > (SELECT AVG(col) FROM ...);
```

#### ☁️ Subconsulta correlata

- Consulta interna depende da externa, executada para cada linha
    

```sql
SELECT * FROM T1 WHERE col > (SELECT AVG(col) FROM T2 WHERE T2.ref = T1.ref);
```

#### ☁️ Com EXISTS / NOT EXISTS

- Verifica existência de resultados na subconsulta
    

```sql
SELECT * FROM T1 WHERE EXISTS (SELECT * FROM T2 WHERE ...);
```

---

### 🔹 3. OPERADORES DE CONJUNTO

|Operador|Função|
|---|---|
|`UNION`|Une resultados diferentes (elimina duplicatas)|
|`UNION ALL`|Une todos (mantém duplicatas)|
|`INTERSECT`|Resultados comuns a ambas as consultas|
|`EXCEPT`|Resultados da primeira, exceto da segunda|

#### Regras:

- Mesmo número de colunas
    
- Tipos de dados compatíveis
    

```sql
SELECT col FROM A UNION SELECT col FROM B;
```

---

### 🖊️ QUESTÕES COMENTADAS

**1.** Qual a diferença entre produto cartesiano e junção?

A) Junção combina todos; produto usa condição  
B) Junção usa condição; produto combina todos os registros  
C) Ambos usam condição  
D) Produto tem condição; junção não  
E) Nenhuma está correta

✅ **Gabarito: B**

> Produto cartesiano gera todas as combinações; junção filtra com base em condição.

---

**2.** O que faz um LEFT JOIN?

A) Retorna apenas os dados com correspondência  
B) Retorna registros da tabela da direita  
C) Retorna todos da esquerda e correspondentes da direita  
D) Retorna registros duplicados  
E) Retorna apenas NULL

✅ **Gabarito: C**

> LEFT JOIN preserva todos os registros da tabela esquerda, preenchendo NULL onde não houver correspondência.

---

**3.** Qual das opções é subconsulta correlata?

A) SELECT * FROM T1 WHERE col IN (SELECT col FROM T2);  
B) SELECT * FROM T1 JOIN T2 ON T1.id = T2.id;  
C) SELECT MAX(col) FROM T1;  
D) SELECT * FROM T1 WHERE col > (SELECT AVG(col) FROM T2 WHERE T1.ref = T2.ref);  
E) SELECT col FROM T1 WHERE id = (SELECT * FROM T2);

✅ **Gabarito: D**

> A subconsulta depende de valores da consulta externa (T1), caracterizando-a como correlata.

---

**4.** Em relação ao operador UNION:

A) Junta dados de duas tabelas sem regra  
B) Junta e aceita colunas diferentes  
C) Junta dados e elimina duplicados  
D) Retorna apenas duplicados  
E) Cria uma nova tabela

✅ **Gabarito: C**

> UNION une dois resultados compatíveis e elimina registros duplicados por padrão.

---

**5.** O que faz o operador EXCEPT?

A) Retorna registros presentes nas duas consultas  
B) Retorna todos os dados duplicados  
C) Retorna registros de A que não estão em B  
D) Junta todas as tabelas  
E) Cria colunas calculadas

✅ **Gabarito: C**

> EXCEPT subtrai o segundo conjunto do primeiro, retornando os dados exclusivos do primeiro.