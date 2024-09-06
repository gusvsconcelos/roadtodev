# **Concepção e modelagem de interface humano-computador**

No processo de desenvolvimento de software, o levantamento de requisitos é uma ==fase crucial em que se compreendem os processos de trabalho dos usuários e suas necessidades.==


### Técnicas de levantamento de requisitos em IHC
- **Entrevistas**
	==É uma conversa guiada por um roteiro de perguntas==, na qual um entrevistador busca obter informação de um entrevistado.
- **Grupos de foco**
	==É um grupo com diversas pessoas reunidas numa espécie de entrevista coletiva==, guiada por um moderador. 
- **Questionários**
	==É um formulário com perguntas que os usuários e demais participantes devem responder== para fornecer os dados necessários em uma pesquisa.
- **Brainstorming**
	*"Tempestade de ideias"*. ==É utilizado para coletar informações sobre as características que os usuários querem em um produto.== Serve para qualquer produto. Seu resultado é uma lista priorizada de necessidades dos usuários.
	
	Para organizar as informações de um _brainstorm_, ==é recomendado o uso da técnica de *diagrama de afinidade*.== Essa técnica organiza ideias de acordo com seus relacionamentos naturais.
- **Classificação de cartões (card sorting)**
	==É uma técnica que não depende de tecnologia.== Consiste em escrever as categorias em papel e espalhá-las em uma área para visualmente fazer a classificação.
- **Estudos de campo**
	==Durante um estudo de campo, são visitados os ambientes onde ocorrem os processos em que o usuário participa.== Trata-se de uma investigação da realidade dos usuários, e não de suposições.
- **Investigação contextual**
	==A investigação contextual ocorre no local onde o usuário trabalha==, de forma que se possa observar o usuário enquanto ele trabalha e conversar com ele sobre o seu trabalho.
- **Storyboard**
	==Técnica que detalha cenários do sistema por meio de uma sequência de desenhos.== Os desenhos também podem ser feitos em papel e colocados em uma área visível aos outros membros das sessões de discussão.
- **Protótipo/maquete**
	==É uma concretização do projeto de interface que permite aos usuários e envolvidos interagirem com ele e explorarem sua aderência às suas necessidades.== É um modelo, uma representação do que pode ser o produto.
	
	**Os protótipos podem ter baixa e alta fidelidade**
	- ***Protótipo de baixa fidelidade***
		==É aquele que não se parece muito com o produto==, mesmo assim é útil porque é simples, de rápida produção, barato e fácil de ser modificado para novos testes.
	- ***Protótipo de alta fidelidade***
		==É aquele que utiliza ferramentas com linguagens mais rápidas de desenvolvimento==, e com isso já mostra ao usuário como vai ficar o ==produto mais próximo da realidade.==

### Técnicas de modelagem de interface

As *técnicas de bridge* e *design centrado no usuário* são fundamentais para definir elementos concretos a partir de conceitos abstratos no design de IHC.

- A *técnica de bridge* ==transforma fluxos de trabalho dos usuários em objetos de tarefas==, testados para garantir correspondência com as atividades reais.

- Já o *design centrado no usuário* é uma abordagem iterativa que especifica o contexto de uso, requisitos, cria a solução de design e ==realiza testes de usabilidade para garantir qualidade==.

##### *Técnica de Bridge*
É baseada numa sequência de sessões com várias pessoas envolvidas no projeto, com a intenção de ==criar “pontes” entre os requisitos dos usuários e da organização==. Em geral, os ==usuários apresentam seu fluxo de trabalho, que são transformados em objetos de tarefas (caixas de diálogo e caixas de mensagens)==. Esses objetos, por sua vez, são testados pelos usuários participantes para verificar se atendem e correspondem às atividades que fazem atualmente e que serão transferidas para o sistema.
##### *Design centrado no usuário*
é uma abordagem *iterativa* que foca especificamente no uso do sistema. ==Essa técnica pressupõe que os designers irão prever como será o uso do sistema== e com isso farão testes de validade desse uso.

Em geral, cada iteração nessa abordagem segue basicamente **quatro etapas**:
- **Etapa 1**
	==Especificação do contexto de uso== onde são definidas as personas, os seus objetivos com o uso do produto e em que condições vão utilizá-lo.
- **Etapa 2**
	==Especificação dos requisitos== que deverão ser atendidos pelo sistema.
- **Etapa 3**
	==Criação da solução== de design da interface.
- **Etapa 4**
	==Avaliação quanto à qualidade== por meio de testes de usabilidade.

### Técnicas para análise e modelagem de tarefas

No campo de IHC, técnicas como *análise hierárquica de tarefas (HTA)*, *GOMS (goals, operators, methods and selection rules, em inglês)* e *ConcurTaskTrees (CTT)* são essenciais para análise e modelagem de tarefas.

A *HTA* ==decompõe objetivos complexos em subobjetivos e operações, facilitando a identificação de problemas e soluções.== O *GOMS* ==descreve tarefas em termos de objetivos, operadores, métodos e regras de seleção==, baseando-se no conhecimento do usuário sobre as ações. Já o *CTT* ==apoia a avaliação do design da interface, explicitando a hierarquia entre tarefas do usuário, sistema, interativas e abstratas==, garantindo uma compreensão clara das relações e dependências entre elas.

##### **Análise hierárquica de tarefas**
Foi desenvolvida para ==entender as competências e habilidades necessárias em tarefas complexas e não repetitivas.== Ajuda a relacionar o que as pessoas fazem, por que fazem, e quais as consequências caso não o façam corretamente.

**HTA em síntese:**
- A HTA examina os objetivos de alto nível e os decompõe em subobjetivos, buscando ==identificar quais **subobjetivos** são mais difíceis de atingir== (ou que geram mais erros).
- Os subobjetivos de um objetivo e as relações entre eles são estabelecidos em um **plano**.
- Um plano define os subobjetivos necessários para alcançar um outro **objetivo maior**
- No plano, cada subobjetivo é alcançado por uma **operação**, que ==é a unidade fundamental em HTA==.

*Uma **operação** é especificada pelas ==circunstâncias nas quais o objetivo é ativado== (input ou entrada), ==pelas atividades ou ações== (actions) que contribuem para atingi-lo e ==pelas condições que indicam o seu atingimento== (feedback).*

*Uma **ação** pode ser entendida como ==uma instrução para fazer algo sob certas circunstâncias==, o **input** ==como estados== e o **feedback** ==como testes ou avaliação do estado final.==*

Dessa maneira, a análise ==visa identificar principalmente como um sistema possibilita ou impede as pessoas de alcançarem seus objetivos==. Essa análise permite ainda ==identificar problemas potenciais de cada ação==, bem como elaborar recomendações para evitá-los.

**A análise hierárquica de tarefas consiste nos seguintes passos:**
1. Definir objetivos.
2. Obter consenso.
3. Identificar as fontes de informação

##### **GOMS (goals, operators, methods, and selection rules)**
Esta técnica ==descreve uma tarefa e o conhecimento do usuário sobre como realizar essa tarefa== em termos de **objetivos (_goals_)**, **operadores (_operators_)**, **métodos (_methods_)** e **regras de seleção (_selection rules_)**.

*Os **objetivos** são as ações que o usuário quer realizar. Os **operadores** permitem que essas ações aconteçam como seleção de menus e o clique de um botão, por exemplo.\*

*Os **métodos** são as sequências de subobjetivos e operadores que fazem com que o usuário atinja seus objetivos.* 

##### Atenção!
>Quando há mais do que um método para atingir um mesmo objetivo, temos então as **regras de seleção**, que serão as tomadas de decisão dos usuários sobre qual método utilizar.

*O **GOMS** trabalha com o conhecimento que uma pessoa tem sobre os processos que executa. ==É mais utilizado quando os usuários executam tarefas sobre as quais já têm bastante conhecimento.==*

###### **CTT (ConcurTaskTrees)**
As árvores de tarefas concorrentes ==servem para apoiar a avaliação do design da interface.==

Tarefas do CTT:
- **Tarefas do usuário**
	Realizadas fora do sistema.
- **Tarefas do sistema**
	Sem interação com o usuário.
- **Tarefas interativas**
	Com diálogos usuário-sistema.
- **Tarefas abstratas**
	Composição de tarefas.

*A maior contribuição dessa técnica é ==explicitar a hierarquia entre as tarefas a serem executadas para atingimento dos objetivos dos usuários.==*