# **Identificar requisitos funcionais de um sistema com uso de Diagrama de Casos de Uso**

## Modelagem de Requisitos e Conceitos de Domínio

A **Unified Modeling Language (UML)** é uma notação visual amplamente usada para especificar sistemas orientados a objetos, adotada como padrão em muitas organizações. ==Seu objetivo é fornecer ferramentas para análise e projeto de sistemas, facilitando a comunicação entre desenvolvedores e partes interessadas.==

**O que é domínio?**
- ==**Domínio** refere-se ao conjunto de características de um grupo de sistemas ou de áreas com funcionalidades similares.==
- Não confundir com "domínio de atributo de classe", que se refere ao conjunto de valores possíveis de um atributo.

## Requisitos Funcionais e Não Funcionais

### *Requisitos*
==Requisitos são condições ou capacidades que um sistema deve satisfazer.== Eles podem ser divididos em dois tipos principais:

1. **Requisitos de Usuário**: Expressam, em linguagem natural, os serviços que o sistema deve fornecer e as restrições de operação.
2. **Requisitos de Sistema**: Descrições técnicas detalhadas das funções e restrições operacionais do software.

### *Requisitos Funcionais*
==Requisitos funcionais descrevem **o que o sistema deve fazer**==, ou seja, os serviços que ele deve fornecer e como ele deve reagir a entradas específicas.

**Exemplos:**
- O sistema deve permitir que o usuário pesquise por nome na base de dados.
- O sistema deve atribuir um identificador único a cada pedido.

*Esses requisitos sempre envolvem a interação do sistema com o usuário.*

### *Requisitos Não Funcionais*
==Requisitos não funcionais descrevem **como o sistema entrega seus serviços**==, incluindo restrições de desempenho, segurança e conformidade com normas.

**Exemplos:**
- O sistema deve estar disponível das 8h30 às 17h nos dias úteis.
- O sistema deve requerer autenticação de usuários.

*Requisitos não funcionais podem ser mais críticos que os funcionais, pois a falha em atendê-los pode inutilizar todo o sistema.*

## Diagrama de Casos de Uso

==O **Diagrama de Casos de Uso** apresenta as funções que o sistema deve realizar do ponto de vista do usuário==, servindo para documentar os requisitos funcionais. 

### *Elementos do Diagrama de Casos de Uso*
1. **Casos de Uso**: ==Representam as funções que o sistema executa, geralmente nomeadas com verbos no infinitivo (e.g., Abrir conta, Sacar dinheiro).== O caso de uso é representado por uma elipse com o nome da função.
   
2. **Atores**: ==São entidades externas que interagem com o sistema, podendo ser usuários humanos, outros sistemas ou hardware.== Eles são representados por um boneco palito no diagrama.

3. **Relacionamentos**: ==Estabelecem conexões entre atores e casos de uso==, entre diferentes casos de uso, ou entre diferentes atores.

### *Tipos de Relacionamento*
- **Comunicação**: ==Conecta atores aos casos de uso== com os quais interagem.
- **Inclusão**: ==Reutiliza passos comuns entre diferentes casos de uso.== Representado por uma linha pontilhada com o estereótipo `<<include>>`.
- **Extensão**: ==Permite que um caso de uso seja estendido por outro==, adicionando comportamentos extras sob certas condições (`<<extend>>`).
- **Generalização**: ==Define uma relação de herança entre atores ou casos de uso.==

### *Atores e Casos de Uso*
- **Atores** ==representam um papel no sistema==, como cliente, funcionário, ou outro sistema com o qual o software interage.
- **Casos de Uso Primários**: ==Relacionados diretamente aos objetivos dos atores.==
- **Casos de Uso Secundários**: ==Não agregam valor diretamente ao usuário, mas são essenciais para o funcionamento do sistema== (e.g., manutenção de cadastros).

### *Exemplo de Relacionamento de Generalização Entre Atores*
- Um ator mais específico (e.g., Supervisor) herda todos os casos de uso de um ator mais genérico (e.g., Vendedor), mas o inverso não ocorre.

## Relacionamentos Entre Casos de Uso

- **Inclusão**: ==Ocorre quando parte de um caso de uso é comum a outros casos==, sendo representado por uma linha pontilhada `<<include>>`. Exemplo: Um caso de uso de "Solicitar prontuário" pode ser incluído tanto em "Fazer pedido de exame" quanto em "Fazer pedido de consulta".
  
- **Extensão**: ==Representa variações no comportamento de um caso de uso.== Exemplo: Durante a "Realização de compra", o sistema pode optar por "Validar limite de crédito", dependendo de uma condição.

## Dicas para Identificação de Atores e Casos de Uso

Durante o levantamento de requisitos, o analista deve identificar quem interage com o sistema e quais são as suas necessidades. **Algumas perguntas úteis são:**
1. **Quem utilizará o sistema (empresas, pessoas)?**
2. **Que outros sistemas ou equipamentos irão se comunicar com o sistema?**
3. **Quem precisa ser informado sobre eventos no sistema?**

## Resumo Final

Os **Diagramas de Casos de Uso** são ferramentas poderosas para entender os requisitos funcionais de um sistema sob a perspectiva dos usuários. ==Eles permitem visualizar a interação dos atores com as funcionalidades do sistema e oferecem um modelo claro para documentar e discutir essas interações.== Por sua simplicidade e flexibilidade, são muito utilizados nas fases iniciais do desenvolvimento, auxiliando tanto os desenvolvedores quanto os usuários a entenderem o comportamento esperado do sistema.

### *Importante*
- Um **caso de uso** é sempre representado por uma funcionalidade que agregue valor ao usuário.
- O **ator** representa quem interage com o sistema, e seus papéis podem variar entre usuários humanos, outros sistemas ou hardware.
- **Relacionamentos** de inclusão, extensão e generalização facilitam a reutilização e organização de casos de uso no diagrama.