# **Componentes para acessibilidade na web**

## Componentes essenciais para acessibilidade na web

Devemos conhecer todos os componentes do ambiente web. São, no total, *sete componentes*: **conteúdo**, **agentes do usuário**, **tecnologia assistiva**, **usuários**, **desenvolvedores**, **ferramentas de autoria** e **ferramentas de avaliação**.

- **Conteúdo**
	==O W3C define como conteúdo todas as informações presentes em uma página web ou aplicação web==, estejam elas disponíveis em formato de texto, imagem, áudio ou codificadas em uma linguagem web, como HTML e CSS.
- **Agente de usuário**
	==Um agente de usuário é qualquer software que apresente o conteúdo web para os usuários.== Os navegadores web como Google Chrome e Mozilla Firefox são agentes de usuários.
- **Tecnologia assistiva**
	Fazendo um paralelo com o mundo físico, assim como algumas pessoas precisam de uma cadeira de rodas (tecnologia assistiva) para explorar a cidade, no ambiente virtual, ==algumas pessoas precisam de leitores de tela (tecnologia assistiva) para navegar na web.==
- **Usuários**
	Reconhecer os diferentes grupos de usuários, seu nível de conhecimento, habilidade e experiência no ambiente web impacta no desenvolvimento de uma web mais acessível.
- **Ferramentas de autoria e  ferramenta de avaliação**
	==Temos outros dois componentes identificados como **“ferramentas de autoria”**, que são os softwares utilizados para desenvolvimento de websites ou conteúdos, como **Drupal** e **WordPress**, e o componente **“ferramentas de avaliação”**, que são ferramentas que avaliam se a página Web está acessível==, segundo critérios, diretrizes e padrões de acessibilidade, como validadores HTML, validadores CSS etc.

## Mas como esses componentes se relacionam?

De modo geral, os “**desenvolvedores**” utilizam “**ferramentas de autoria**” e “**ferramentas de avaliação**” para criar “**conteúdo**” na web. Os “**usuários**” utilizam navegadores web ou outros “**agentes de usuário**” ou “**tecnologias assistivas**” para acessar e interagir com o conteúdo.

- **Desenvolvedores**
	Ferramentas de aperfeiçoamento e ferramentas de criação.
- **Usuários**
	Navegadores e players de mídia e tecnologias assistivas.

## Como isso funciona na prática?

**Todos os sete componentes devem trabalhar em conjunto.**
- **Especificações técnicas**
	Definem como especificar o atributo (exemplo em HTML atributo alt no elemento `<img>`).
- **Diretrizes WAI (WCAG, ATAG, UAAG)**
	Definem como implementar o atributo.
- **Desenvolvedores**
	Fornecem o texto alternativo apropriado.
- **Ferramentas de Autoria**
	Facilitam e promovem o fornecimento de texto alternativo.
- **Ferramentas de Avaliação**
	Ajudam a verificar se existe texto alternativo.
- **Agentes de Usuário**
	Fornecem uma interface humana e de máquina para o texto alternativo.
- **Tecnologia Assistiva**
	Fornecem uma interface humana e de máquina para o texto alternativo em diferentes formas.
- **Usuários**
	Acessam o texto alternativo.

## Diretrizes e padrões de acessibilidade do W3C

O grupo de trabalho **WAI** (*Web Accessibility Initiative*) do W3C é responsável pelo desenvolvimento dos padrões de acessibilidade na web para os diferentes componentes, **conforme destacado a seguir**:
### *Componentes e Diretrizes*
- **Ferramentas de autoria**
	Diretrizes de acessibilidade para ferramentas de autoria (Authoring Tool Accessibility Guidelines - *ATAG*).
- **Conteúdos, desenvolvedores, ferramentas de autoria e ferramentas de avaliação**
	Diretrizes de acessibilidade para conteúdo na Web (Web Content Accessibility Guidelines - *WCAG*).
- **Agentes de usuário: Navegadores Web, players de mídia e alguns aspectos de tecnologias assistivas**
	Diretrizes de acessibilidade para agente de usuário (User Agent Accessibility Guidelines - *UAAG*).

## Visão geral das diretrizes de acessibilidade

- **ATG**
	Possuem dois principais objetivos: ==apoiar o desenvolvimento de ferramentas de autoria acessíveis==, possibilitando que pessoas com deficiência criem conteúdo na web e apoiar os usuários conteudistas na criação de um conteúdo web mais acessível, em conformidade com as Diretrizes de Acessibilidade para Conteúdo da Web (WCAG).
- **UAAG**
	==A UAAG é voltada para desenvolvedores de navegadores da web, extensões de navegador e outros aplicativos que processem o conteúdo web.==
- **WCAG**
	==Têm como objetivo orientar o desenvolvimento de conteúdo web mais acessível== em desktops, laptops, tablets e dispositivos móveis.

## Um mergulho nas diretrizes de acessibilidade para conteúdo web (WCAG)

**As WCAG 2.1 são estruturadas em quatro camadas:**
- *Quatro princípios* servem como base para que qualquer pessoa possa acessar e usar o conteúdo da web: **perceptível**, **operável**, **compreensível** e **robusto**.
- *Treze diretrizes* ajudam os autores a compreender os critérios de sucesso e a melhor implementar as técnicas.
- *78 critérios de sucesso testáveis*.
- Variedade de técnicas com orientações para atingir os critérios de sucesso.

## WCAG 2.1 - Os quatro princípios

1. **Perceptível**
	As informações e os componentes da interface do usuário devem ser apresentados em formas que possam ser percebidas pelo usuário.
2. **Operável**
	Os componentes de interface de usuário e a navegação devem ser operáveis.
3. **Compreensível**
	A informação e a operação da interface de usuário devem ser compreensíveis.
4. **Robusto**
	O conteúdo deve ser robusto o suficiente para poder ser interpretado de forma confiável por uma ampla variedade de agentes de usuário, incluindo tecnologias assistivas.

**As diretrizes referentes a cada um dos quatro princípios:**
1. **Perceptível**
	- Alternativas em texto
	- Mídias com base em tempo
	- Adaptável
	- Discernível
2. **Operável**
	- Acessível pelo teclado
	- Tempo suficiente
	- Convulsões e reações físicas
	- Navegável
	- Modalidades de entrada
3. **Compreensível**
	- Legível
	- Previsível
	- Assistência de entrada
4. **Robusto**
	- Compatível

## WCAG 2.1 ‒ Os 78 Critérios de Sucesso (CS)

A base para se determinar se o conteúdo atende às diretrizes das WCAG 2.1 são os **78 critérios de sucesso.**

**Exemplos de critérios de sucesso, para cada um dos princípios das WCAG 2.1:**
1. **Perceptível**
	Diretriz 1.3: **Adaptável**  
	Critério de Sucesso 1.3.1. **Informações e relações** (Nível A): =="as informações, a estrutura, e os relacionamentos transmitidos através de apresentação podem ser determinados por meio de código de programação ou estarem disponíveis no texto".==
2. **Operável**
	Diretriz 2.4. **Navegável**  
	Critério de Sucesso 2.4.5. **Várias formas** (Nível AA): =="está disponível mais de uma forma para localizar uma página web em um conjunto de páginas web, exceto quando a página web for o resultado, ou uma etapa, de um processo".==
1. **Compreensível**
	Diretriz 3.1. **Legível**  
	Critério de Sucesso 3.1.3. **Palavras incomuns** (Nível AAA): =="um mecanismo para identificar definições específicas de palavras ou expressões utilizadas de uma forma restrita e incomum está disponível, incluindo expressões idiomáticas e jargões".==
1. **Robusto**
	Diretriz 4.1. **Compatível**  
	Critério de sucesso 4.1.1. **Análise** (Nível A): =="no conteúdo implementado utilizando linguagens de marcação, os elementos dispõem de “tags” completas de início e de fim, os elementos são aninhados de acordo com as respectivas especificações, os elementos não contêm atributos duplicados, e quaisquer IDs são exclusivos, exceto quando as especificações permitem estas características".==

- *Testar os critérios de sucesso envolve uma combinação de testes automatizados e avaliação humana por especialistas em acessibilidade.*
- *Embora o conteúdo deva satisfazer a todos os critérios de sucesso, nem sempre estão acessíveis a uma grande variedade de deficiências.*
- *Testes funcionais devem ser realizados com objetivo de verificar se o conteúdo funciona como esperado ou se satisfaz o critério de sucesso. Portanto, testes de acessibilidade são recomendáveis com testes funcionais.*
- *Testes de usabilidade definem a facilidade de uso na execução de certa tarefa.*

## WCAG 2.1 ‒ Os três níveis de conformidade (A, AA, AAA)

Cada um dos 78 critérios de sucesso possui um nível de conformidade que varia de **A** (mínimo) a **AAA** (máximo). Para que uma página da web esteja em conformidade com as WCAG 2.1, **os seguintes requisitos de conformidade devem ser atendidos:**
- **Nível A**
	É o nível mínimo de acessibilidade. Para atingir o nível "A", o conteúdo web deve satisfazer 30 critérios de sucesso, ou fornecer conteúdo alternativo em conformidade com o respectivo nível.
- **Nível AA**
	**Para atingir o nível "AA", o conteúdo web deverá:**
	- Satisfazer todos os 30 critérios de sucesso de nível "A".
	- Os 25 critérios de sucesso de nível" AA".
- **Nível AAA**
	**Para atingir o nível "AAA" (o nível máximo de acessibilidade), o conteúdo web deverá:**
	- Satisfazer todos os 30 critérios de sucesso de nível "A".
	- Os 20 critérios de sucesso de nível" AA".
	- Os 28 critérios de sucesso do nível "AAA".

***Não é recomendável** que o nível “AAA” seja considerado como meta, devido à impossibilidade de satisfazê-lo em sua totalidade para alguns tipos de conteúdo.*