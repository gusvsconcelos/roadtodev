# **Distinguir os conceitos e pilares de análise e projeto orientados a objetos**

## Paradigma orientado a objetos

- **Qualquer coisa do mundo real é um objeto**
- **Objetos realizam tarefas requisitando serviços a outros objetos**
- **Os objetos similares são agrupados em classes e cada objeto pertence a uma classe**
- **A classe determina o comportamento possível a um objeto**
- **Classes são organizadas em hierarquias**

## Conceitos fundamentais da orientação a objetos

- **Classe**
	Abstração das características de um grupo de coisas do mundo real.  
- **Objeto**
	Um elemento específico de uma classe ou uma instância de uma classe.
- **Operação**
	É o nome dado a cada ação (função) que o objeto sabe realizar.
- **Mensagem**
	Quando um objeto precisa de um serviço da responsabilidade de outro, ele precisa enviar uma *mensagem* a ele. ==Cada mensagem ativa uma das operações do objeto.==
- **Estado**
	Por definição, chama-se *estado do objeto* o conjunto de valores de seus atributos em dado momento.

## Os pilares da orientação a objetos

- **Abstração**
- **Encapsulamento**
- **Herança**
- **Polimorfismo**

## Orientação a objetos como elemento de reusabilidade e extensibilidade

**A orientação a objetos minimiza a gestão da complexidade na medida em que permite uma organização mais adequada de seus componentes, além de seu reaproveitamento.**

- **Reusabilidade**
	O uso de componentes já escritos pode ser a base para outros softwares (através da herança).
- **Extensibilidade**
	Novos componentes podem ser desenvolvidos a partir de outros, já desenvolvidos, sem afetar o comportamento do componente de origem (mediante o princípio do polimorfismo) e permitindo que esse comportamento seja alterado, estendido para um novo contexto.

## Análise de sistemas orientada a objetos

**De forma simples, pode-se dizer que a atividade de análise visa identificar o que os usuários e os demais interessados (que juntos formam os _stakeholders_) precisam que o sistema faça.**

**A atividade de análise costuma ser dividida em:**
- **Levantamento de requisitos**
- **Análise dos requisitos**

*A sua finalidade é construir a melhor solução, que possa ser implementada em qualquer tecnologia, de acordo com as disponíveis no mercado, naquele momento.*

### *Levantamento de requisitos*
- **O foco é na compreensão do problema.**
- **As necessidades e os desejos que os usuários têm são, tecnicamente, chamados de *requisitos*.**

**O produto gerado por essa fase é o *documento de requisitos*, que contém todos os requisitos necessários ao sistema, classificados em:**
- **Requisitos funcionais**
	Declaram as funcionalidades necessárias ao sistema.
- **Requisitos não funcionais**
	Apresentam algumas características associadas a uma, algumas ou todas as funcionalidades, e dizem respeito a aspectos de qualidade, confiabilidade, desempenho, portabilidade, segurança e usabilidade do sistema.

### *Análise de requisitos*
A fase de análise de requisitos é a transposição dos registros dos requisitos funcionais e não funcionais para os modelos que a equipe pretende usar.

**A análise de requisitos tem, minimamente, duas perspectivas ou visões:**
- **Análise do domínio (ou do negócio)**
	Visa a identificar ou modelar os objetos que serão usados na aplicação.
- **Análise da aplicação**
	Sucede a análise do domínio. Nela, são identificados os objetos de análise que não fazem sentido para os analistas de domínio, mas que são fundamentais para atender às funcionalidades necessárias ao sistema, a aplicação em si.

Os principais diagramas UML usados nas fases de análise são: *diagramas de casos de uso* e *diagrama de classes*. Além desses, ajudam também *diagramas de interação* e de *estados*, em alguns casos.

==Análise pode ser traduzida em ****”faça a coisa certa”.==

## Projeto (desenho) de sistemas orientado a objetos

==A atividade de projeto denota uma solução, voltada a atender aos requisitos identificados na fase de análise==, considerando os recursos tecnológicos necessários para implementar os objetos do domínio e os objetos da aplicação.

O objetivo é decidir “como o sistema funcionará” para atender aos requisitos.

O projeto, portanto, deriva da análise e produz uma descrição dos recursos computacionais e de como o sistema deve executar no dia a dia.

**A fase de projeto pode ser dividida em:**
-  **Projeto da arquitetura**
	Ato de distribuir as classes de análise em subsistemas com seus componentes, bem como distribuir os componentes pelos recursos de hardware disponíveis.
	
	Dentre os diagramas da UML, usamos aqui os *diagramas de pacotes*, *componentes* e *implantação*.
- **Projeto Detalhado**
	Compreende atividades como **modelagem das colaborações entre os objetos**, **projeto da interface**, **projeto do banco de dados** e **aspectos computacionais de alto nível.** 
	
	Dentre os diagramas UML usados aqui, destacam-se: *diagrama de interação*, *atividades*, *detalhamento do diagrama de classes*, de *estados*, dentre outros detalhados adiante.

==Projeto pode ser traduzido em **“faça certo a coisa”**.==

## Desenvolvimento de sistemas em camadas

No início da computação, os sistemas eram **monolíticos**, ou seja, todo o código ficava confinado numa única camada. À medida que os sistemas cresceram e se tornaram complexos, a manutenção ficou mais difícil e a divisão em camadas foi uma das soluções encontradas para o projeto de arquitetura de um software.

Num primeiro momento, a rede cliente-servidor, naturalmente, dividiu o software em duas camadas: a camada de código que roda no cliente e a camada servidor. Com o advento da web, separou-se em três e depois em quatro camadas. ==Atualmente, pode-se criar tantas camadas quantas sejam necessárias, em função do tipo de aplicação.==

**As camadas em geral:**
- Possuem alta coesão e baixo acoplamento.
- Possuem propósito bem definido.  
- ==A camada superior tem conhecimento apenas da imediatamente inferior==, que fornece os serviços, por uma interface.

**As vantagens e desvantagens do desenvolvimento de software em camadas:**
 **Vantagens**
- Torna o código mais organizado e legível.  
- Permite o desenvolvimento, o teste e a manutenção das camadas isoladamente.  
- Permite melhor reuso do código ou dos objetos.  
- Pode substituir uma tecnologia que implemente uma camada, de forma simples, sem interferir nas demais.
- Disciplina as dependências entre as camadas.  
- Mais adaptável a uma quantidade maior de usuários.

 **Desvantagens**
- Aumenta o número de classes do sistema.  
- A adição de camadas torna o sistema mais complexo.  
- Potencialmente, reduz o desempenho do software.

**Como exemplo, podemos citar o modelo de camadas mais usado nos últimos anos, o de três camadas, que engloba as camadas de:**
- **Apresentação**
	Compreende as classes do sistema que permitem a interação com o usuário, as chamadas classes de fronteira.
- **Negócio**
	Compreende as classes responsáveis pelos serviços e pelas regras do negócio, ou seja, reúne as classes de controle e negócio.
- **Dados**
	Responsável pelo armazenamento e pela recuperação dos dados persistentes do sistema, ou seja, as classes de persistência de dados.