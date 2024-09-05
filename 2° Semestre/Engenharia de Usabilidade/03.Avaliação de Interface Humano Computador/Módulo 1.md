# **Reconhecer a importância da avaliação de usabilidade de uma interface humano-computador**

*Sistemas interativos* recebem informações dos usuários e provêm respostas através de suas funcionalidades. Mais ainda, alguns sistemas apoiam a interação entre usuários diferentes, como é o caso das *redes sociais*. ==Este tipo de sistema precisa ser simples, fácil de usar, e deve permitir que o usuário realize as suas tarefas de forma eficiente e com satisfação.== Este atributo de qualidade de um software é chamado de **usabilidade**.

### Relevância da avaliação de interface humano-computador

*A avaliação de interfaces é uma atividade fundamental em qualquer processo de desenvolvimento de software que tenha como meta produzir um sistema interativo com alta qualidade de uso.*

**BARBOSA e SILVA (2010) apontam os benefícios da avaliação da interface humano-computador:**

- Os problemas podem ser corrigidos antes do produto entrar em operação;
- A equipe de desenvolvimento pode se concentrar na solução de problemas reais;
- Os engenheiros sabem construir um sistema interativo, mas geralmente não sabem discutir a qualidade de uso do sistema;
- O tempo para colocar o produto no mercado diminui, pois os problemas são corrigidos logo no início do processo de desenvolvimento;
- Identificar e corrigir os problemas na interface humano-computador permitem entregar um produto mais robusto.

No entanto, ==é difícil garantir a qualidade total de um produto de software.== Isso porque, na prática, seria necessário avaliá-lo em todas as situações de uso possíveis. Além de ser inviável prever todas essas situações, o custo seria alto demais, pois exigiria muito tempo e esforço para sua realização. ==Por isso, existem várias técnicas que podem ser usadas na avaliação, cobrindo aspectos e formas diferentes de avaliar.== Devemos então escolher a mais adequada para o contexto do sistema que estamos querendo avaliar.

### Objeto da avaliação de interface humano-computador

De acordo com **Barbosa e Silva (2010)**, ==um sistema interativo deve ser avaliado sob as perspectivas de todos os envolvidos==: Quem o concebe (projetista), quem o constrói (desenvolvedores), e quem o utiliza (usuários).

**O desenvolvedor utiliza várias técnicas de avaliação, que compõem a chamada etapa de testes do processo de desenvolvimento de software. Por exemplo:**
- **Testes de unidade**
	Checar o funcionamento de cada item do programa.
- **Testes de integração**
	Verificar se todos os itens do programa se comunicam corretamente.
- **Testes de sistema**
	Verificar o funcionamento do sistema como um todo.
- **Testes de operação**
	Testar o sistema com usuários.

*Também é comum classificarmos os testes como **testes de caixa-branca (o código é testado)** e **caixa-preta (o sistema é testado).***

### Contextos de avaliação de interface humano-computador

**Em relação ao ‘quando avaliar’, classificamos as avaliações em dois tipos: Formativa e somativa.**
- **Avaliação formativa**
	É conduzida ao longo de todo o processo de desenvolvimento ==com objetivo de garantir o entendimento sobre o que os usuários querem e precisam.==
- **Avaliação somativa**
	É realizada sobre a solução, completa ou parcial, de acordo com o escopo do projeto, mas apenas no final do processo de desenvolvimento. A avaliação somativa ==julga a qualidade de uso de uma interface==, buscando evidências que indiquem que os objetivos foram atingidos.

**Outra questão relacionada ao contexto de uma avaliação de interface humano-computador é o ambiente (local) de avaliação. Neste sentido, as avaliações, que envolvem diretamente a participação dos usuários, podem ser realizadas em contexto real de uso ou em laboratório.**
- **Contexto real de uso**
	A avaliação no ambiente real do usuário ==permite ampliar a observação de casos típicos de uso==, que não seriam percebidos em uma avaliação em laboratório.
- **Laboratório**
	A avaliação em laboratório, por outro lado, ==oferece um controle maior==, e permite que o avaliador defina e interfira no ambiente como um todo e na forma de interação do usuário com o sistema.

Dependendo do tipo de avaliação, ==o avaliador pode coletar dados sobre os aspectos positivos e negativos identificados durante o uso do sistema==, e, as necessidades e oportunidades de intervenção. A abrangência e o foco da coleta de dados devem ser definidos de acordo com os objetivos da avaliação.

**Cada técnica de avaliação foca em dados e resultados de diferentes tipos.**
- **Dados qualitativos**
	Representam conceitos que ==não são representados numericamente.==
- **Dados quantitativos**
	==Representam numericamente== uma quantidade, ou seja, uma grandeza resultante de uma contagem ou medição.

### Tipos de técnicas de avaliação humano-computador

==Cada técnica atende melhor a certos objetivos de avaliação==, orienta quando e onde os dados devem ser coletados, como eles devem ser analisados, e quais critérios de qualidade de uso se deseja avaliar

- **Investigação**
	As técnicas de investigação ==envolvem o uso de questionários, a realização de entrevistas, grupo focal, estudos de campo, entre outros.==
- **Inspeção**
	As técnicas de inspeção ==permitem ao avaliador examinar uma solução de IHC para tentar antever as possíveis consequências de certas decisões de design== sobre as experiências de uso.
- **Observação de uso**
	As técnicas de observação ==fornecem dados sobre situações em que os usuários realizam suas atividades==, com ou sem apoio de sistemas interativos.

Para decidir qual técnica (ou quais técnicas) adotar, o avaliador deve levar em consideração vários aspectos, tais como: ==limite de prazo, orçamento previsto, equipamentos necessários, número de usuários disponíveis para participar, número de avaliadores capacitados em cada técnica, e outros recursos que sejam necessários em cada caso.==

**As técnicas de avaliação de interface seguem, em geral, os seguintes passos: preparação, execução ou coleta de dados, análise e interpretação dos dados, consolidação e relato dos resultados. Veja um pouco mais sobre cada um deles:**
- **Preparação**
	Como primeiro passo para preparar uma avaliação, ==o avaliador deve entender a situação atual, que inclui o domínio do problema, os papéis e perfis dos usuários, seus objetivos e atividades, e o contexto em que o sistema é ou será utilizado.==
- **Execução ou coleta de dados**
	A coleta de dados deve ocorrer ==conforme o planejamento realizado e a técnica de avaliação selecionada.==
- **Análise e interpretação dos dados**
	Na atividade de interpretação de dados, ==o avaliador analisa o material coletado de acordo com o que foi definido durante a atividade de preparação da avaliação.==
- **Consolidação e relato dos resultados**
	Uma vez concluída a interpretação individual dos dados coletados, seja das previsões dos avaliadores ou das observações das experiências de uso dos participantes, ==os resultados são consolidados e analisados em conjunto, para os avaliadores tentarem identificar repetições nos resultados, de acordo com a técnica selecionada.==

### Framework DECIDE

Preece, Sharp e Rogers (2013) apresentaram um framework chamado **DECIDE** com objetivo de ==orientar o planejamento, a execução e a análise de uma avaliação de IHC.== O framework ==**DECIDE** é composto por seis etapas onde as iniciais compõem o nome (em inglês):==

***D** - Determinar (Determine)*
- Determinar as metas e os objetivos da avaliação.
***E** - Explorar (Explore)*
- Explorar as questões cuja avaliação pretende responder para transformar os objetivos iniciais em operacionais.
***C** - Escolher (Choose)*
- Escolher os métodos e as técnicas que responderão às questões da avaliação.
***I** - Identificar (Identify)*
- Identificar questões práticas a serem abordadas pela avaliação.
***D** - Decidir (Decide)*
- Decidir como lidar com as questões éticas envolvidas.
***E** - Avaliar (Evaluate)*
- Avaliar, interpretar e apresentar os dados.

*É importante também ressaltar que os resultados de uma avaliação de interface ==normalmente indicam tendências de problemas, e não uma certeza de que eles vão ocorrer durante o uso do sistema.==*