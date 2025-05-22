## ✅ RESUMO PARA PROVAS – MODELAGEM LÓGICA E FÍSICA DE BANCO DE DADOS

---

### 🔹 OBJETIVOS DO TEMA

- Compreender o **modelo relacional** e seus componentes.
    
- Executar o processo de **normalização** (1FN, 2FN, 3FN).
    
- Aplicar **mapeamento conceitual-lógico**.
    
- Conhecer aspectos da **modelagem física** no SGBD.
    

---

### 🔹 ELEMENTOS DO MODELO RELACIONAL

- **Tabela (relação)**: estrutura com **linhas (tuplas)** e **colunas (atributos)**.
    
- **Nome da tabela**: deve ser único e indicar o objeto representado.
    
- **Colunas**:
    
    - Devem ter **nome único**.
        
    - Devem conter **valores atômicos** e **monovalorados**.
        
    - Possuem **domínio** (tipo de dado).
        
    - Podem ser **obrigatórias ou opcionais** (NULL).
        
- **Linhas**: representam instâncias da entidade (ex: um aluno).
    

#### 🔹 Chave Primária

- Garante **unicidade**, **valor obrigatório** e **monovalorado**.
    
- Pode ser:
    
    - **Simples** (1 atributo)
        
    - **Composta** (2+ atributos)
        
    - **Mínima** (sem atributos desnecessários)
        
- **Chave candidata**: qualquer atributo que pode ser PK.
    
- **Chave alternativa**: chave candidata não escolhida como PK.
    

#### 🔹 Chave Estrangeira (FK)

- Liga tabelas diferentes.
    
- Deve referenciar um valor existente em outra tabela.
    
- Impõe **restrições de integridade referencial**:
    
    - FK deve estar presente na PK referenciada.
        
    - FK deve se atualizar junto à PK.
        
    - Não é possível excluir PK referenciada se houver FK vinculada.
        

#### 🔹 Esquemas

- **Diagramas** (ex: notção "pé de galinha") representam tabelas, PK, FK e tipos.
    
- **Esquema textual**: representação em texto das tabelas, chaves e relacionamentos.
    

---

### 🔹 NORMALIZAÇÃO

#### 🏛 Objetivo

- Melhorar **consistência** e **integridade**.
    
- Evitar **redundância** e **anomalias**.
    

#### ① Primeira Forma Normal (1FN)

- Elimina **atributos compostos** e **multivalorados**.
    
- Garante valores atômicos nas colunas.
    
- Divide dados em tabelas separadas conforme necessidade.
    

#### ② Segunda Forma Normal (2FN)

- Requer que a tabela esteja na 1FN.
    
- Elimina **dependências funcionais parciais** (coluna depende de parte da PK composta).
    
- Cria novas tabelas para separar dados dependentes apenas de parte da PK.
    

#### ③ Terceira Forma Normal (3FN)

- Requer que a tabela esteja na 2FN.
    
- Elimina **dependências funcionais transitivas** (coluna depende de coluna não-chave).
    
- Cria tabela separada com dados dependentes transitivamente.
    

---

### 🔹 MAPEAMENTO CONCEITUAL-LÓGICO

#### 🔍 Objetivo

- Converter DER (modelo conceitual) em **modelo relacional** (lógico).
    
- Etapas:
    
    1. Mapeamento de entidades
        
    2. Mapeamento de relacionamentos
        
    3. Mapeamento de atributos multivalorados
        
    4. Mapeamento de especialização/generalização
        

#### 🔹 Mapeamento de Entidades

- **Entidade forte** → vira tabela com atributos como colunas e PK.
    
- **Entidade fraca** → vira tabela com FK + PK composta.
    

#### 🔹 Mapeamento de Relacionamentos

- Depende da **cardinalidade**:
    
    - 1:1 → fusão de tabelas ou FK em uma tabela.
        
    - 1:N → FK na tabela do lado N.
        
    - N:N → cria tabela própria com FK de ambas as tabelas.
        
    - Ternário → tabela própria com 3 FK e atributos do relacionamento.
        

#### 🔹 Mapeamento de Atributos Multivalorados

- Criar nova tabela com FK da entidade original + atributo multivalorado.
    
- PK composta: FK + atributo multivalorado.
    

#### 🔹 Mapeamento de Especialização/Generalização

- Três soluções:
    
    1. **Tabela única** com coluna tipo
        
    2. **Tabelas separadas** com FK da entidade genérica
        
    3. **Subdivisão da genérica** (sem tabela para genérica)
        

---

### 🖊️ QUESTÕES COMENTADAS

**1.** Qual é a função da chave primária em uma tabela relacional?

A) Realizar cálculos automáticos  
B) Repetir registros para backup  
C) Garantir unicidade e identificação exclusiva de registros  
D) Organizar visualmente a tabela  
E) Separar atributos compostos

✅ **Gabarito: C**

> A chave primária garante que cada registro da tabela seja único, mantendo a integridade de dados.

---

**2.** Qual das alternativas caracteriza uma tabela na 1FN?

A) Contém colunas com tipos de dados diferentes  
B) Possui atributos compostos e multivalorados  
C) Todas as colunas têm valores atômicos e monovalorados  
D) Permite relações N:N entre colunas  
E) Contém atributos com dependências transitivas

✅ **Gabarito: C**

> 1FN exige que cada coluna contenha apenas valores indivisíveis (atômicos).

---

**3.** Para estar na 2FN, uma tabela deve:

A) Ter atributos compostos  
B) Eliminar dependências parciais da chave primária  
C) Ter apenas uma chave estrangeira  
D) Usar apenas dados numéricos  
E) Estar normalizada até a 3FN

✅ **Gabarito: B**

> A 2FN elimina dependências em que um atributo depende apenas de parte da chave primária composta.

---

**4.** No mapeamento de relacionamentos N:N, o procedimento correto é:

A) Fundir as duas tabelas  
B) Criar FK em uma das tabelas  
C) Criar nova tabela com duas FK e chave primária composta  
D) Ignorar o relacionamento  
E) Transformar o relacionamento em atributo

✅ **Gabarito: C**

> Um relacionamento N:N precisa de uma tabela própria que contenha as chaves estrangeiras e possivelmente atributos adicionais.

---

**5.** No mapeamento de especialização/generalização, qual opção representa a **solução II**?

A) Criar tabela única com coluna TIPO  
B) Tabelas separadas com FK da entidade genérica  
C) Subdivisão da entidade genérica em tabelas especializadas  
D) Tabela com apenas PK da genérica  
E) Ignorar a herança

✅ **Gabarito: B**

> A solução II cria uma tabela para a entidade genérica e uma para cada especializada, com FK ligada à genérica.

---

Se quiser, posso converter esse resumo em **PDF** com capa ou em **flashcards** interativos.