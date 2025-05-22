## ✅ RESUMO PARA PROVAS – SISTEMAS DE BANCO DE DADOS (SBD)

---

### 🔹 CONCEITOS BÁSICOS E HISTÓRICO

- **Banco de Dados (BD)**: coleção de dados relacionados, com significado e organizados para uso posterior.
    
- **SBD**: sistema completo, incluindo BD, SGBD e aplicações.
    
- **SGBD**: software intermediário entre aplicações e dados armazenados.
    

#### Evolução:

- **Anos 1940**: computadores para cálculos (Babbage, von Neumann).
    
- **Anos 1950**: disco magnético (DASD) permitiu acesso direto aos dados.
    
- **Anos 1960**: surgem os SGBD, com independência entre dados e programas.
    

#### Sistemas de arquivos vs SBD:

- Em sistemas de arquivos, cada programa controla seu próprio acesso aos dados.
    
- No SBD, o SGBD centraliza a gerência e fornece **independência de dados**.
    

#### Tipos iniciais de SGBD:

- **Hierárquico (IMS)**: estrutura em árvore
    
- **Rede (IDS/CODASYL)**: estrutura em grafo
    
- Ambos são **navegacionais**: navega-se entre registros
    

#### Modelo relacional (Codd, 1970):

- Baseado em **relações matemáticas** (tabelas)
    
- Usa a linguagem **SQL**
    
- Simplificou e padronizou o acesso aos dados
    

---

### 🔹 SGBD RELACIONAIS E EVOLUÇÃO

#### Principais SGBD:

- **Oracle**: líder comercial, suporta múltiplos modelos
    
- **MySQL**: open source, usado em aplicações web
    
- **SQL Server**: desenvolvido com base no Sybase, popular no ambiente Windows
    
- **PostgreSQL**: relacional-objeto, open source, destaque em ensino e pesquisa
    
- **DB2 (IBM)**: robusto, multiplataforma
    

#### Modelos NoSQL ("Not Only SQL"):

- Atendem às demandas de **big data**, **IoT**, **ciência de dados**
    
- Exemplos: MongoDB (documentos), Neo4J (grafos), Redis (chave-valor), Cassandra (colunar)
    
- Alguns SGBD atuais são **multimodelos** (relacional + NoSQL)
    

---

### 🔹 CARACTERÍSTICAS DOS SBD

#### Independência de dados:

- **Física**: alterações na estrutura de armazenamento não afetam o modelo lógico
    
- **Lógica**: alterações no modelo lógico não afetam as visões externas (usuários)
    

#### Arquitetura ANSI/SPARC (3 esquemas):

- **Interno**: armazenamento físico
    
- **Conceitual**: estrutura lógica do banco
    
- **Externo**: visões dos usuários
    

#### Diferenças entre SBD e sistemas de arquivos:

- **Natureza autocontida**: inclui metadados
    
- **Abstração de dados**: oculta detalhes físicos
    
- **Compartilhamento e concorrência**: ACID
    

#### Modelos de dados:

- **Físico**: descreve o armazenamento
    
- **Lógico**: representa a estrutura (relacional, documentos, grafos...)
    
- **Conceitual**: visão do usuário (modelo ER, UML)
    

---

### 🔹 FUNCIONALIDADES DOS SBD

- **Redução de redundância**
    
- **Compartilhamento multiusuário (concorrência)**
    
- **Controle de acesso e segurança**
    
- **Restrições de integridade**
    
- **Recuperação (backup e recovery)**
    
- **Interfaces variadas para acesso aos dados**
    

#### Propriedades ACID:

- **Atomicidade**: tudo ou nada
    
- **Consistência**: mantém as regras
    
- **Isolamento**: execução concorrente sem interferência
    
- **Durabilidade**: dados persistem após falhas
    

#### Vantagens:

- Consistência e integridade dos dados
    
- Padronização e economia de escala
    
- Facilidade de manutenção e expansão
    

#### Desvantagens:

- Overhead do SGBD
    
- Custo de implementação e treinamento
    
- Pode não ser ideal para sistemas pequenos ou de tempo real
    

---

### 🔹 PAPÉIS EM SISTEMAS DE BANCO DE DADOS

- **Administrador de aplicações**: cuida das aplicações em execução
    
- **Administrador de desenvolvimento**: participa do desenvolvimento de sistemas
    
- **Administrador de dados (AD)**: define padrões, políticas e regras de negócio
    
- **Administrador de banco de dados (DBA)**: gerencia os objetos do banco, permissões, estrutura
    
- **Administrador de sistema**: gerencia hardware e SO
    

---

### 🔹 ARQUITETURA DOS SGBD

#### Componentes:

- **Metadados**: dados sobre dados (armazenados no catálogo)
    
- **Banco de dados**: dados propriamente ditos
    
- **SGBD**: software intermediário entre aplicações e banco de dados
    

#### Módulos:

- **Linguagem de definição de dados (DDL)**: cria/edita objetos (CREATE, DROP)
    
- **Linguagem de controle de dados (DCL)**: permissões (GRANT, REVOKE)
    
- **Linguagem de manipulação de dados (DML)**: acessa dados (SELECT, INSERT...)
    
- **Processador de runtime**: executa consultas e transações (nó central do SGBD)
    
- **Gerenciador de dados armazenados**: executa I/O
    

#### Tipos de usuários:

- **Usuários casuais**: consultas ad hoc
    
- **Usuários paramétricos**: interação por parâmetros (ex: reservas)
    
- **Programadores**: desenvolvem sistemas com comandos embutidos (SQL)
    

---

### 🔹 POSTGRESQL (EXEMPLO DE SGBD RELACIONAL)

- **Origem**: projeto Ingres (Universidade da Califórnia)
    
- **Modelo relacional-objeto**
    
- **Open source**, licença BSD
    
- **Multiplataforma**, altamente escalável
    
- Suporte completo a:
    
    - SQL
        
    - ACID
        
    - Triggers, visões, stored procedures
        
    - Replicação, backup online, PiTR
        
    - Indexações: B-tree, GiST, hash, etc.
        

#### Recursos avançados:

- **Herança de tabelas**
    
- **Sistema de regras (reescrita de queries)**
    
- **Sistema de eventos (LISTEN/NOTIFY)**
    
- **Extensões**: PostGIS, OpenFTS, PL/pgSQL
    
- **Modelo cliente/servidor**: processo backend (`postgres`) e clientes (`psql`, `pgadmin`, etc.)
    

---

## 🖊️ QUESTÕES COMENTADAS – SISTEMAS DE BANCO DE DADOS

**1.** Qual a principal vantagem do modelo relacional criado por Codd?

A) Uso de grafos para representar os dados  
B) Estrutura em árvore hierárquica  
C) Simplicidade conceitual (tabelas) baseada em função matemática  
D) Navegação entre registros por ponteiros  
E) Uso exclusivo da linguagem COBOL

✅ **Gabarito: C**

> O modelo relacional usa tabelas com base em matemática de relações, com simplicidade e rigor.

---

**2.** Qual das propriedades abaixo garante que o banco de dados permanece consistente após falhas?

A) Atomicidade  
B) Durabilidade  
C) Isolamento  
D) Consistência  
E) Integridade

✅ **Gabarito: D**

> A consistência garante que o banco esteja sempre em um estado válido antes e após cada transação.

---

**3.** No modelo de três esquemas, qual representa a visão do usuário?

A) Interno  
B) Conceitual  
C) Externo  
D) Físico  
E) Relacional

✅ **Gabarito: C**

> O esquema externo define visões individuais adaptadas às necessidades dos usuários.

---

**4.** Qual alternativa define corretamente metadados?

A) Dados armazenados temporariamente  
B) Códigos de programa do SGBD  
C) Dados que descrevem dados  
D) Dados irrelevantes ao banco  
E) Transações compiladas

✅ **Gabarito: C**

> Metadados descrevem estruturas e restrições do banco de dados. Estão no catálogo.

---

**5.** Qual papel é responsável por definir regras de negócio e políticas de dados?

A) Administrador de sistema  
B) DBA  
C) Administrador de aplicações  
D) Administrador de dados  
E) Desenvolvedor

✅ **Gabarito: D**

> O Administrador de Dados define regras, padrões e políticas sobre os recursos de dados da organização.

---

Se quiser, posso gerar esse resumo como **PDF**, **flashcards** ou **mapa mental** para facilitar a revisão!