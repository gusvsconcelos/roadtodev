# **Modelagem de Negócios e de Dados na Metodologia RAD**

## 1. Visão Geral

### Objetivo

- Formalizar como o sistema será estruturado e representado.
- Usa diagramas visuais para facilitar entendimento e validação com stakeholders.

> 📝 *Modelagem conecta ideias e implementações.*

---
## 2. Modelagem de Negócios

### Finalidade

- Traduzir os processos do negócio para o sistema.
- Foco em **processos**, **ciclo de dados** e **requisitos comerciais**.

### Técnicas Utilizadas

#### *Casos de Uso (UML)*

Representa a interação entre atores e o sistema.

- **Atores:** Usuários ou sistemas externos

#### *Tipos de Processos no Caso de Uso*

| **Tipo**      | **Exemplo (Restaurante)**            |
| ------------- | ------------------------------------ |
| Principais    | Marketing, serviços de almoço/jantar |
| Auxiliares    | Compras de insumos                   |
| Gerenciamento | Controle de pessoal, relatórios      |

#### *Boas práticas*

- Cada caso de uso **deve estar vinculado a um ator**.
- Evite redundância: **generalize casos semelhantes**.
- Mantenha o escopo **restrito ao necessário**.

---
## 3. Modelagem de Dados

### Conceito

- Representação **formal** dos dados, relacionamentos e regras de negócio.
- Base para criação do **banco de dados** e conformidade (ex: **LGPD**).

### Técnicas Usadas

- **Modelo Entidade-Relacionamento (E-R)**
- **UML (Diagrama de Classes)**

### Tipos de Modelos

| **Modelo**   | **Finalidade**                                      | **Características**                                       |
| ------------ | --------------------------------------------------- | --------------------------------------------------------- |
| *Conceitual* | Representa entidades, atributos e relacionamentos   | Independente de tecnologia. Foco: entendimento do negócio |
| *Lógico*     | Define estrutura e regras técnicas dos dados        | Base para o físico. Otimizado para desempenho e segurança |
| *Físico*     | Descreve como os dados serão implementados no banco | Define tabelas, campos, tipos, chaves, índices etc.       |

#### *Elementos do Modelo Conceitual*

- **Entidade:** Aluno, Escola
- **Atributo:** Nome, Endereço
- **Relacionamento:** Uma escola possui vários alunos

---
## 4. Considerações Estratégicas

### Relação com a Metodologia RAD

> ⚠️ *RAD ≠ Modelagem fixa*

- A modelagem **evolui com os protótipos**.
- O modelo de dados deve **estabilizar rápido** para focar em regras de negócio e **UX**.

### Competências do Dev RAD

- Formação sólida
- Raciocínio lógico apurado
- Capacidade de adaptação
- Boa comunicação com clientes

---
## Conclusão

**Modelagem de Negócios**: Define o *"o que"* e *"como"* os processos empresariais serão representados.

**Modelagem de Dados**: Define *"quais dados"*, *"como se relacionam"* e *"como serão armazenados"*.

- Juntas, elas garantem que o sistema atenda à realidade do negócio e seja tecnicamente viável.

> 💡 *RAD sem modelagem sólida = Entrega rápida com retrabalho certo.*