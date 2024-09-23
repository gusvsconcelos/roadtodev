# **Identificar classes e seus relacionamentos em um domínio de aplicação com uso de Diagrama de Classes**

## Elementos de uma Classe:

- **Atributos**: ==São as características dos objetos que serão armazenadas.== Possuem visibilidade (*pública*, *protegida*, *privada*, ou *de pacote*) e podem ter valores iniciais.
- **Operações**: Ações que a classe pode realizar, também com diferentes níveis de visibilidade. ==As operações são métodos que os objetos compartilham.==

## Visibilidade:

- **Pública (+)**: Atributo acessível por qualquer objeto.
- **Protegida (#)**: Atributo acessível por subclasses.
- **Privada (-)**: Atributo acessível apenas dentro da própria classe.
- **De pacote (~)**: Atributo acessível para classes dentro do mesmo pacote.

## Relacionamentos no Diagrama de Classes:

1. **Associação**: ==Ligação entre classes==, representada por uma linha que indica a interação entre objetos dessas classes. Ela pode incluir:
   - **Nome**: Usado para descrever o relacionamento.
   - **Multiplicidade**: Define quantos objetos estão relacionados.
   - **Direção de leitura**: Indica como ler a associação.
   - **Papéis**: Identifica o papel dos objetos na relação.
   - **Classe associativa**: Usada quando há necessidade de armazenar informações sobre a associação.

2. **Autoassociação**: ==Relaciona objetos da mesma classe==, mas com diferentes papéis.

3. **Relacionamento todo-parte (Agregação e Composição)**:
   - **Agregação**: A parte pode existir independentemente do todo.
   - **Composição**: A parte depende da existência do todo.

4. **Herança (Generalização/Especialização)**: ==Relacionamento hierárquico entre classes==, onde subclasses herdam atributos e operações de superclasses.