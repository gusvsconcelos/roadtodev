# **Empregar os diagramas de interação no projeto de sistema.**

## Ciclo de Vida de Desenvolvimento de Software (SDLC):

**O processo de desenvolvimento de software envolve várias etapas essenciais, independentemente da metodologia adotada:**
1. **Levantamento de requisitos**
2. **Análise**
3. **Projeto (design)**
4. **Implementação**
5. **Testes**
6. **Implantação**

==Essas fases são interdependentes, ou seja, cada uma depende dos artefatos produzidos pela anterior.==

## Modelos da Fase de Análise vs. Fase de Projeto

==A UML não determina uma ordem fixa para a criação de diagramas, mas os **diagramas de interação** são fundamentais na fase de projeto==, mostrando o comportamento dinâmico de um sistema através do fluxo de mensagens e o relacionamento entre objetos.

### *Diagramas de Interação*
Esses diagramas são usados para representar as **comunicações** entre objetos dentro de um sistema, fornecendo um **contexto para as interações** e o comportamento de um sistema em tempo real. ==Eles são essenciais para fornecer detalhes adicionais ao modelo de classes e ao modelo de casos de uso.==

**Os diagramas de interação mais comuns são:**
1. **Diagrama de Sequência**: Focado no tempo e sequência de eventos.
2. **Diagrama de Comunicação**: Focado na troca de mensagens entre objetos.

### *Diagrama de Sequência*
==Descreve a **sequência temporal** das comunicações entre objetos em um sistema.==

**Usado para:**
  - Documentar casos de uso.
  - Verificar se as operações das classes foram identificadas.
  - Validar a necessidade de objetos para o sistema.

**Elementos do Diagrama de Sequência:**
1. **Objetos**: Representados no topo do diagrama, associados a uma **linha da vida**.
2. **Linha da Vida**: Representa a vida do objeto ao longo do tempo.
3. **Mensagens**: Representadas por setas, mostrando a comunicação entre os objetos.

### *Mensagens no Diagrama de Sequência*
- **Síncronas**: Solicitações que aguardam resposta.
- **Assíncronas**: Solicitações que não esperam retorno imediato.
- **De Retorno**: Mensagens que retornam uma resposta.
- **De Criação**: Mensagens que criam objetos.

==Mensagens podem ser condicionais ou iterativas, representando loops e alternativas no fluxo de execução.==

### *Diagrama de Comunicação*
- Enfatiza como os objetos estão **vinculados** e trocam mensagens entre si.
- As mensagens são numeradas para mostrar a ordem das interações.
- Este diagrama é útil para visualizar a estrutura de comunicação entre objetos.

## Como Construir um Diagrama de Interação

1. **Identificar o caso de uso** a ser modelado.
2. **Identificar os objetos** que participam da interação.
3. **Determinar os relacionamentos** e a sequência de mensagens.
4. **Selecionar o tipo de diagrama** (sequência ou comunicação).
5. **Rotular os elementos** do diagrama de forma clara.

### *Dicas Práticas*
- ==É recomendado iniciar o diagrama com a representação da **mensagem de ativação** do sistema==, separando a lógica do domínio da interface com o usuário.
- Durante a construção do diagrama, podem ser incluídas notas explicativas e modularizações para simplificar a compreensão.

### *Relação entre Modelos de Análise e Projeto*
- O modelo de interações pode ser construído tanto na fase de análise quanto na de projeto.
- Na fase de projeto, ele é refinado, incluindo detalhes sobre a criação e destruição de objetos e o tipo de mensagens trocadas.

==Os modelos de **casos de uso**, **classes** e **interações** são interdependentes==, formando um ciclo evolutivo ao longo do desenvolvimento do sistema.