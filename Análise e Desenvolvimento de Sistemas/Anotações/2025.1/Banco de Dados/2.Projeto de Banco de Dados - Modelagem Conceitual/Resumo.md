## ✅ RESUMO PARA PROVAS – PROJETO DE BANCO DE DADOS: MODELAGEM CONCEITUAL

---

### 🔹 ETAPAS DO PROJETO DE BANCO DE DADOS

#### 1. **Levantamento de requisitos**

- Entrevistas com usuários para entender o funcionamento do negócio
    
- Documentação dos requisitos de dados (ex: clientes, cursos, inscrições)
    

#### 2. **Projeto conceitual**

- Criação de um **modelo de dados de alto nível** (independente de tecnologia)
    
- Uso do **DER (Diagrama Entidade-Relacionamento)**
    
    - Entidades: retângulos (ex: CLIENTE)
        
    - Relacionamentos: losangos (ex: FAZ)
        
    - Atributos: elipses conectadas
        
- Finalidade: representar de forma abstrata o negócio
    

#### 3. **Projeto lógico**

- Conversão do modelo conceitual para estrutura lógica conforme SGBD
    
- Normalmente usa o **modelo relacional**
    
    - Entidades → tabelas
        
    - Relacionamentos → tabelas com chaves estrangeiras
        

#### 4. **Projeto físico**

- Detalhes de implementação: tipos de dados, índices, null/not null, chaves
    
- Depende do **SGBD escolhido** (Ex: PostgreSQL)
    
- Usa **SQL (DDL)** para criação das tabelas
    

---

### 🔹 ELEMENTOS DO DER

#### Entidade

- Representa conjunto de objetos reais ou abstratos
    
- Ex: CLIENTE, CURSO, DISCIPLINA
    

#### Relacionamento

- Associação entre entidades
    
- Ex: CLIENTE **faz** INSCRIÇÃO em CURSO
    
- Pode ser binário, ternário ou autorrelacionamento
    

#### Atributo

- Propriedade de uma entidade ou relacionamento
    
- Tipos:
    
    - Simples (ex: nome)
        
    - Composto (ex: endereço = rua, número...)
        
    - Identificador (PK): valor único (ex: CPF)
        
    - Multivalorado: mais de um valor (ex: telefones)
        
    - Opcional: pode ser nulo (cardinalidade 0)
        

#### Cardinalidade

- Define o número mínimo e máximo de ocorrências
    
- (0,1), (1,1), (0,N), (1,N)
    

---

### 🔹 EXTENSÕES DO MODELO ER

#### Especialização / Generalização

- Hierarquia entre entidades
    
- Ex: FUNCIONÁRIO pode ser DOCENTE ou ANALISTA
    
- Classificações:
    
    - Total ou Parcial
        
    - Exclusiva ou Compartilhada
        

#### Entidade associativa

- Quando um relacionamento precisa de atributos próprios
    
- Ex: INSCRIÇÃO com data e status entre CLIENTE e CURSO
    

#### Entidade fraca

- Depende de outra entidade para existir (identificação parcial)
    

#### Entidade isolada

- Sem relacionamento com outras (ex: dados institucionais da IES)
    

#### Relacionamento N:N

- Pode ser transformado em entidade com dois relacionamentos 1:N
    

---

### 🔹 PRÁTICAS DE MODELAGEM

#### Restrições de integridade

- Podem ser expressas:
    
    - No DER (ex: cardinalidade)
        
    - Via texto (restrição semântica: data fim > data início)
        

#### Modelagem descendente (top-down)

1. Identifica entidades e relacionamentos
    
2. Define atributos, identificadores, cardinalidades
    
3. Valida junto ao usuário
    

#### Atributo vs Entidade

- Usa-se **entidade** quando:
    
    - Há vários valores (multivalorado)
        
    - Possui atributos ou relacionamentos próprios
        
- Usa-se **atributo** quando for simples e direto
    

#### Atributo opcional

- Valor nulo permitido (cardinalidade mínima 0)
    

#### Atributo redundante

- Deve ser evitado se puder ser calculado a partir de outro dado
    

#### Atributo composto

- Subdivisível em partes com significado próprio (ex: endereço)
    

---

### 🖊️ QUESTÕES COMENTADAS – MODELAGEM CONCEITUAL

**1.** Qual etapa do projeto de BD define a estrutura do banco sem se preocupar com implementação?

A) Projeto físico  
B) Projeto lógico  
C) Levantamento de requisitos  
D) Projeto conceitual  
E) Normalização

✅ **Gabarito: D**

> O projeto conceitual usa o DER para representar o negócio de forma abstrata, sem depender de tecnologia.

---

**2.** Em um DER, o que caracteriza um atributo como identificador?

A) Possuir valor nulo  
B) Ser derivado de outro atributo  
C) Ter valor único por instância  
D) Ser composto por mais de um campo  
E) Ser opcional

✅ **Gabarito: C**

> Um atributo identificador deve distinguir unicamente cada instância de entidade (como CPF ou id).

---

**3.** Quando devemos modelar uma entidade associativa?

A) Quando queremos representar atributos de um relacionamento  
B) Quando uma entidade possui atributos opcionais  
C) Quando há relacionamento 1:1  
D) Quando entidades possuem atributos compostos  
E) Quando há apenas um atributo simples

✅ **Gabarito: A**

> A entidade associativa é usada quando um relacionamento precisa armazenar atributos (como data de inscrição).

---

**4.** Qual o principal objetivo da especialização/generalização?

A) Otimizar desempenho de consulta  
B) Evitar uso de atributos compostos  
C) Representar hierarquias de classes no mundo real  
D) Reduzir redundância  
E) Melhorar integração com SGBD relacional

✅ **Gabarito: C**

> Esse recurso permite representar subtipos e supertipos, organizando entidades por similaridade e herança.

---

**5.** Quando devemos transformar um relacionamento N:N em entidade?

A) Quando possui atributos  
B) Quando não há chave estrangeira  
C) Quando se deseja modelar integridade referencial  
D) Quando ambos os lados possuem cardinalidade (0,1)  
E) Quando não há chave primária

✅ **Gabarito: A**

> Um relacionamento N:N com atributos deve ser transformado em entidade associativa com relacionamentos 1:N.

---

Quer que eu gere este resumo como **PDF** com capa, ou em **formato de flashcards** para estudar melhor?