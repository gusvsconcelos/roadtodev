# **Produzir o documento de requisitos para um estudo de caso de modelagem de sistemas**

## Processo de Desenvolvimento de Software

O desenvolvimento de software é composto por atividades típicas que devem estar presentes em qualquer processo de desenvolvimento.

==A UML==, no contexto de sistemas orientados a objetos, ==é amplamente utilizada para produzir artefatos de software, sejam gráficos (diagramas) ou textuais.==

## Diagramas da UML

**Diagramas da UML são divididos em:**
 - **Diagramas de Estrutura** (ou estáticos): exemplos incluem *Diagramas de Classes*, *Componentes*, *Objetos*, *Pacotes*.
 - **Diagramas de Comportamento** (ou dinâmicos): exemplos incluem *Diagramas de Sequência*, *Casos de Uso*, *Estados*, *Atividades*.

**Exemplos de Diagramas:**
- **Diagrama de Classes**: define atributos, métodos e relacionamentos entre classes.
- **Diagrama de Casos de Uso**: mostra a interação de usuários com o sistema.
- **Diagrama de Sequência**: foca nas interações temporais entre objetos.

## Levantamento de Requisitos

==A **elicitação de requisitos** tem como objetivo entender o problema e alinhar as necessidades dos usuários com a visão da equipe de desenvolvimento.==

**Técnicas comuns incluem:**
- Entrevistas com usuários e especialistas.
- Observação do ambiente.
- Análise de sistemas semelhantes.

## Estudo de Caso: Pousadas Férias no Nordeste

**Contexto:**
A empresa fictícia quer desenvolver um sistema de gestão de reservas de quartos online, cobrindo aspectos de reserva, precificação e pagamento de diárias e produtos consumidos pelos hóspedes.

## Requisitos Funcionais (RF)

**Exemplos:**
- **RF 1**: O sistema deve permitir reservas online ou por telefone.
- **RF 3**: O sistema cobra uma diária no cartão de crédito para confirmação de reservas online.
- **RF 9**: O sistema deve registrar os consumos de produtos pelos clientes.
  
## Requisitos Não Funcionais (RNF)

**Exemplos**:
 - **RNF 1**: O sistema deve utilizar tecnologia Web.
 - **RNF 2**: O SGBD será o MySQL.
 - **RNF 6**: O processo de desenvolvimento será conduzido com a metodologia Scrum.

## Regras de Negócio (RN)

**Exemplos:**
- **RN 1**: Uma reserva é realizada por um único cliente.
- **RN 3**: A pré-reserva exige um depósito bancário de 40% do total da reserva.
- **RN 6**: Cancelamentos com menos de 24h ou não comparecimento resultam na cobrança de uma diária.