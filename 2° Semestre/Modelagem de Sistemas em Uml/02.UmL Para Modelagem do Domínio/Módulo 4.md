# **Empregar Diagramas de Objetos e de Pacotes para apoiar a especificação de um sistema**

## Diagrama de Objetos

==O **Diagrama de Objetos** na UML representa uma instância específica de um **Diagrama de Classes** em um momento determinado.== Ele exibe uma "fotografia" de como os objetos se relacionam e quais são os valores de seus atributos naquele instante.

### *Características principais*
- Foca em objetos e não em classes.
- ==A semelhança com o Diagrama de Classes é visual, mas ele mostra a situação de objetos específicos e suas associações em um momento particular.==
- Cada objeto tem uma **identificação única** e os valores de seus atributos são exibidos. Caso esses valores mudem, o estado do objeto também muda.

### *Estrutura*
**Os objetos são representados por um retângulo com dois compartimentos:**
  1. O compartimento superior apresenta o nome do objeto, sublinhado. Exemplo: `Marta:Professor`.
  2. O compartimento inferior exibe os valores dos atributos (opcional).

### *Aplicações*
- Validação do **Diagrama de Classes**.
- Ilustração de estados específicos dos objetos.
- Análise de uma situação ou interação específica.

==Apesar de serem raramente utilizados na prática, os Diagramas de Objetos podem ser úteis para esclarecer dúvidas sobre o modelo.==

## Diagrama de Pacotes

==Um **Diagrama de Pacotes** é utilizado para agrupar elementos como classes, casos de uso ou até outros pacotes, organizando o sistema em componentes menores e mais compreensíveis.==

### *Principais características*
- Cada pacote agrupa elementos de forma coesa.
- Pacotes podem formar hierarquias e se relacionar entre si por meio de **relações de dependência**.
- Visibilidade dos elementos dentro do pacote:
  - `+` (público) – *visível por todos.*
  - `#` (protegido) – *visível por pacotes filhos.*
  - `-` (privado) – *visível apenas dentro do próprio pacote.*

### *Aplicações*
- Organizar sistemas grandes e complexos.
- Representar a **arquitetura** de sistemas, como o padrão **MVC** (Model-View-Control).
- Mostrar a dependência entre módulos e suas relações.

==Um **pacote bem estruturado** é coeso, fracamente acoplado e possui um conjunto equilibrado de elementos.==

*Em suma, esses diagramas são essenciais para modelar aspectos diferentes de um sistema, desde a visão mais granular, com os objetos em um estado específico, até a visão mais ampla, representando como os elementos do sistema estão organizados e interconectados.*