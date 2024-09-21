# **Descrever as visões, a síntese geral e os diagramas da UML**

## O que é UML, afinal?

A UML é uma linguagem padrão para construção de projetos de sistemas, voltada para a visualização, a especificação, a construção e a documentação de artefatos de um sistema.

A UML é uma linguagem de modelagem, ==**não é um método de desenvolvimento nem tampouco uma metodologia ou um processo de desenvolvimento de sistemas**==, uma vez que não determina a ordem e nem como os diagramas devem ser usados.

**A UML é uma linguagem destinada a:**
- **Visualização**
	==A modelagem gráfica facilita a compreensão do sistema e das decisões tomadas em análise e projeto==, além de melhorar a comunicação entre a equipe, permitindo sua interpretação sem ambiguidades.
- **Especificação**
	==Permite a construção de modelos precisos, não ambíguos e completos sob diferentes visões== e atendendo às necessidades de modelagem das diferentes fases do processo de desenvolvimento de software, independentemente do processo ou modelo usado.
- **Construção**
	==Os diagramas UML podem ser integrados às principais e mais populares linguagens de programação do mercado==, tais como Java e C++. Mas, para isso, terá que buscar uma solução integrada de **ferramenta CASE (_Computer-Aided Software Engineering_)** que gere código fonte (para linguagens específicas) a partir de alguns diagramas UML.

>**RESUMINDO**
>
> A UML é uma linguagem de modelagem padronizada.
>   
> **• ==A UML é independente de tecnologia==, adequando-se a todo método, metodologia ou processo de desenvolvimento.**
>
> **• ==A UML não diz quais diagramas usar e nem em que ordem==, pois a metodologia de desenvolvimento ditará essa ordem.**
>
> **• A UML disponibiliza diagramas sob diferentes visões ou perspectivas.**

## Visões da UML

- **Visão de casos de uso**
	==A visão de caso de uso permite olhar o sistema sob o ponto de vista externo, do usuário==, descrevendo seu comportamento por conjunto de interações usuário-sistema.
- **Visão de projeto (ou lógica)**
	==Permite visualizar o sistema sob o ponto de vista de sua estrutura interna e seu comportamento==, em resposta às funcionalidades externamente percebidas por seus usuários. Enfatiza os *pacotes*, as *classes*, as *interfaces*, os *subsistemas* (pacotes) e as *colaborações*.
- **Visão de implementação (ou de desenvolvimento)**
	==Compreende o gerenciamento das versões do sistema, ou seja, de suas implementações utilizáveis por seus usuários.== Compreendem os *componentes*, *subsistemas* e arquivos que compõem fisicamente o sistema.
- **Visão de implantação (ou física)**
	==Enfatiza a distribuição física do sistema em suas partes (subsistemas e componentes) e as respectivas conexões entre elas.== Enfatiza também a organização física dos computadores e as conexões entre eles (a rede de computadores).
- **Visão de processo**
	==Enfatiza aspectos físicos mais peculiares como concorrência, sincronismo entre sistemas e desempenho== (performance, confiabilidade, tolerância a falhas e outros aspectos) do sistema, considerando os processos e os processadores.

**A UML implementa diagramas que atuam nas cinco visões descritas anteriormente, permitindo ampla modelagem sobre todos os aspectos (visões) relevantes do sistema.**

## UML e integração com processos de desenvolvimento

*A UML é independente de metodologia e processo de desenvolvimento. Isso é positivo para os fabricantes de software que implementam UML, pois não limita seu mercado.*

*A UML pode ser usada de diversas formas, desde esboços manuais para interação com usuários ou equipe, passando pelo uso de ferramentas de diagramação UML até sofisticadas ferramentas CASE, que integram os modelos e geram código em linguagens específicas.*

**A UML então pode ser adaptada em qualquer processo, seja ele:**
- **Em cascata**
	Com e sem retroalimentação, ==onde as fases se sucedem, a seguinte inicia quando a anterior termina.== A desvantagem é que, se for sem retroalimentação, não há opção de retorno à fase anterior.
- **Iterativo**
	==Onde o sistema é dividido em subconjuntos de funcionalidades (com mínimo de dependência com os demais conjuntos)==, e as atividades de análise, projeto, implementação, teste e implantação são realizadas a cada subconjunto. 
- **Ágil**
	==Os processos são ditos ágeis porque compartilham um conjunto de valores e princípios definido pelo manifesto ágil.== O foco aqui é permitir modificação sempre que preciso e no desenvolvimento de código. A modelagem existe, mas em menor escala e com ênfase na comunicação com usuário e equipe de desenvolvimento.
- **RUP (_Rational Unified Process_)**
	==O RUP é uma estrutura de processo, que vai usar casos de desenvolvimentos (processo a ser usado), a maioria deles iterativos.== O RUP não se adapta a processo em cascata.

## Visão geral dos diagramas UML

- **Os diagramas estruturais**
	==Dizem respeito às estruturas estáticas necessárias ao sistema==, como os *pacotes*, as *classes*, os *objetos*, os *componentes* e a *estrutura de nós* (estruturas computacionais). ==Também são chamados de estruturas estáticas.==
- **Os diagramas comportamentais**
	Evidenciam o comportamento (funcionamento) de parte de um sistema ou processo de negócio relacionado ao sistema, segundo determinada perspectiva. ==Dizem respeito às funcionalidades do sistema, aos estados de um objeto em seu ciclo de vida, às interações entre os objetos, dentre outros aspectos. Também são chamados de diagramas dinâmicos.==

![[diagramas-uml.jpg]]

## Diagramas UML e sua utilização nas fases

### *Diagramas UML na atividade de análise*

| Levantamento de requisitos                                                                                      | Análise de requisitos                                                                                                                    |
| --------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| Esboço inicial do **diagrama de pacotes**, para grandes sistemas, evidenciando a necessidade de particionamento | Detalhamento e aprofundamento do **diagrama de pacotes**                                                                                 |
| Esboço inicial do **diagrama de casos de uso**                                                                  | Detalhamento e aprofundamento do **diagrama de casos de uso**                                                                            |
| Esboço inicial do **diagrama conceitual de classes**, em alto nível (sem detalhes)                              | Detalhamento e aprofundamento do **diagrama conceitual de classes**                                                                      |
|                                                                                                                 | **Diagrama de estados**, para os objetos mais complexos durante seu ciclo de vida                                                        |
|                                                                                                                 | **Diagrama de atividades**, para elucidar um processo ou fluxo de trabalho relevante ou ainda para elucidar um caso de uso mais complexo |
### *Diagramas UML na atividade de projeto*

|                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Adição de detalhes ao **diagrama conceitual de classes**, que passa a ser o **diagrama de classes de projeto**.                                                    |
| **Diagrama de sequência ou diagrama de comunicação**, para cenários de uso mais relevantes, o que ajuda a identificar métodos das classes envolvidas na interação. |
| Detalhamento dos **diagramas de estados** elaborados na atividade de análise, podendo modelar de outros objetos percebidos.                                        |
| **Diagrama de componentes**, caso o software use algum já pronto ou a ser construído.                                                                              |
| **Diagrama de implantação**, evidenciando as unidades computacionais e alocando os componentes nelas.                                                              |
| **Diagrama de atividades**, esclarecendo métodos de classes mais complexos ou que usem processamento paralelo.                                                     |