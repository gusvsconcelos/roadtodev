# **Construir os modelos de análise para um estudo de caso de modelagem de sistemas em UML** 

## Modelo de Classes

Após identificar as funcionalidades no modelo de casos de uso, o próximo passo é desenvolver o **modelo de classes**, que mostra a estrutura estática do sistema, como as classes e seus relacionamentos. ==Este modelo é essencial para entender como os objetos do sistema colaboram para atingir as funcionalidades desejadas.==

**Principais pontos:**
- O **modelo de classes** na etapa de análise não contém detalhes completos da solução, focando apenas na identificação de classes, atributos e associações.
- As **associações** entre classes podem ser simples ou mais complexas, como a agregação, composição e generalização/especialização (herança).
- O **diagrama de classes** para o caso de uso "Registrar Reserva" envolve classes como **Cliente**, **Funcionário**, **Reserva**, **Pousada**, **Quarto**, **Tipo de Quarto**, **Preço da Diária**, entre outros.
  
**As abstrações identificam classes e seus relacionamentos, como:**
- **Pessoa** é a superclasse de **Cliente** e **Funcionário**.
- Uma **Reserva** pode estar associada a 0 ou mais **Funcionários**, dependendo se foi feita online ou por telefone.
- A associação entre **Quarto** e **Pousada** é uma composição: o quarto só existe se a pousada existir.

## Modelo de Atividades

==O **modelo de atividades** descreve os aspectos dinâmicos do sistema, detalhando as etapas de um processo.== No diagrama de atividades, são definidos os passos que representam a execução de uma tarefa. 

No caso de uso "Registrar Reserva", o diagrama inclui dois atores: **Cliente/Recepção** e **Sistema**, distribuídos em raias. **O fluxo principal envolve:**
- O sistema busca pousadas disponíveis.
- O cliente informa a pousada e as datas.
- O sistema lista os quartos disponíveis.
- O cliente escolhe o quarto e a quantidade de pessoas.

O **fluxo alternativo** acontece se a reserva for feita por telefone, com a necessidade de login do funcionário da recepção.

## Modelo de Estados

==O **modelo de estados** mostra as mudanças de estado de um objeto em resposta a eventos.== O exemplo apresentado se refere à classe **Reserva**, que pode iniciar nos estados "Em validação" ou "Confirmada", dependendo de como a reserva foi feita (telefone ou online).

As transições de estado são disparadas por eventos, e podem incluir condições de guarda e ações, como no caso da transição de "Em validação" para "Confirmada" após o cliente fazer o depósito de pré-reserva.