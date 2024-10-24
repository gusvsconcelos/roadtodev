# **Serviços da camada de aplicação**

## Protocolos da Camada de Aplicação

Um **protocolo de camada de aplicação** define como duas ou mais aplicações, executando em sistemas diferentes, trocam mensagens entre si. Para que haja essa comunicação estruturada, o protocolo define regras específicas sobre:

- **Tipos de mensagens**: Quais são as mensagens permitidas, como requisição e resposta.
- **Sintaxe das mensagens**: Estrutura das mensagens, como os campos que devem ser incluídos e como são organizados.
- **Semântica dos campos**: O significado das informações em cada campo.
- **Regras de comunicação**: Quando e como enviar e responder mensagens.

Esses protocolos são fundamentais para garantir que aplicações em diferentes dispositivos possam se entender, mesmo sendo desenvolvidas por entidades diferentes. Na Internet, esses protocolos são definidos por **RFCs (Request for Comments)**, documentos públicos que especificam como os protocolos devem funcionar.

## Serviços e Protocolos da Camada de Aplicação na Internet

### *Serviço Web – Protocolo HTTP*
O **HTTP (Hypertext Transfer Protocol)** é o protocolo que possibilita o funcionamento da web. Toda vez que acessamos um site, nosso navegador (cliente) se comunica com um servidor web por meio do HTTP, pedindo o conteúdo (como páginas HTML) e recebendo as respostas para exibir o site.

- **Requisição**: O cliente (navegador) envia uma mensagem ao servidor, pedindo uma página web.
- **Resposta**: O servidor envia o conteúdo solicitado de volta ao navegador.

Esse protocolo é **stateless**, o que significa que cada requisição é independente, e o servidor não mantém memória sobre as interações anteriores.

### *Serviço de Correio Eletrônico – Protocolos SMTP, IMAP e POP3*
Os e-mails são enviados e recebidos por meio de protocolos de camada de aplicação, como:

- **SMTP (Simple Mail Transfer Protocol)**: Utilizado para o **envio** de e-mails. Ele garante que as mensagens saiam do cliente e cheguem ao servidor de e-mail.
- **POP3 (Post Office Protocol)**: Usado para o **recebimento** de e-mails. Ele permite que o cliente baixe as mensagens do servidor para seu dispositivo e as exclua do servidor.
- **IMAP (Internet Message Access Protocol)**: Também usado para **receber** e-mails, mas diferente do POP3, o IMAP mantém as mensagens no servidor, permitindo que sejam acessadas de diferentes dispositivos.

### *Serviço de Nomes – DNS*
O **DNS (Domain Name System)** é o serviço que traduz nomes de domínio, como "www.google.com", em endereços IP que os computadores utilizam para se comunicar.

- **Requisição DNS**: O cliente (seu navegador, por exemplo) solicita a tradução de um nome de domínio para um endereço IP.
- **Resposta DNS**: O servidor DNS retorna o endereço IP correspondente ao domínio solicitado.

## Serviço WEB

### *HTTP*
O **protocolo HTTP** (Hypertext Transfer Protocol) é a base para a transferência de páginas web na internet, definido pelas RFCs 1945 e 2616. Ele foi criado no CERN em 1991 como uma maneira de facilitar a troca de informações entre cientistas por meio de hipertextos, e foi demonstrado pela primeira vez na conferência Hypertext91.

### *Funcionamento do Protocolo HTTP*
O HTTP é dividido em duas etapas principais, e utiliza o protocolo **TCP** para garantir a confiabilidade na entrega das mensagens.

**Etapa 1: Solicitação da Página Web**
1. O usuário digita o endereço de uma página no navegador ou clica em um hiperlink.
2. Esse endereço aponta para um documento HTML, que pode conter texto, imagens, vídeos e outros objetos.
3. Para que o servidor envie essa página ao navegador, o cliente (navegador) faz uma **requisição HTTP**, que segue um padrão de comunicação:
   - A requisição é iniciada com a palavra **GET**.
   - O cliente especifica a página que deseja, o protocolo utilizado (HTTP) e o servidor que será contatado.

**Etapa 2: Transferência da Página**
1. A requisição HTTP é enviada ao servidor utilizando o **protocolo TCP**. O TCP garante que os dados cheguem ao destino de forma confiável e sem erros.
2. O servidor processa a solicitação e responde com o conteúdo da página requisitada, enviando os dados de volta ao cliente (navegador), que exibirá a página ao usuário.

### *Detalhes Técnicos Importantes*
- **HTML**: A linguagem utilizada para estruturar as páginas web. Ela define como o conteúdo será exibido para o usuário.
- **ASCII**: Utilizado para codificar as informações na requisição HTTP, é um padrão que representa símbolos e caracteres em formato binário.
- **TCP**: Um protocolo de transporte confiável que garante que as mensagens entre cliente e servidor sejam entregues corretamente, sem erros ou dados perdidos.

## Serviço de correio eletrônico

### *Evolução do Correio Eletrônico*
Nos primórdios, os sistemas de correio eletrônico eram bem simples, permitindo apenas a troca de arquivos, onde o destinatário era indicado na primeira linha do texto. Com o passar do tempo, novas necessidades surgiram, como enviar mensagens em diferentes idiomas e com caracteres especiais. 

Para resolver essas limitações, surgiram as **RFCs 821 e 822** em 1982, que definiram o protocolo de transmissão (SMTP) e o formato da mensagem, mas ainda restringiam o texto ao código **ASCII**. Essa limitação fez com que surgisse o **MIME (Multipurpose Internet Mail Extensions)**, permitindo o envio de mensagens com diferentes formatos e conteúdo multimídia.

### *Arquitetura do Sistema de Correio Eletrônico*
A arquitetura do correio eletrônico é baseada em dois principais agentes:

1. **Agente do Usuário**: Este é o software que os usuários utilizam para interagir com o sistema de correio. Ele permite que os usuários:
   - Enviem e recebam mensagens e anexos.
   - Leiam, arquivem e excluam mensagens.
   - Escrevam novas mensagens e anexem arquivos.
   
2. **Agente de Transferência de Mensagens**: Também conhecidos como servidores de correio eletrônico, são responsáveis por encaminhar as mensagens ao seu destino. Exemplos incluem:
   - Postfix
   - Zimbra
   - Exchange

### *Funcionamento do Correio Eletrônico*
Vamos analisar como funciona uma comunicação entre dois usuários, por exemplo, Orlando e Maria:

1. **Envio da Mensagem**:
   - Orlando compõe uma mensagem em seu agente do usuário e solicita seu envio.
   - A mensagem é encaminhada ao agente de transferência de mensagens de Orlando, que analisa e encaminha ao agente de Maria.

2. **Recebimento da Mensagem**:
   - O agente de transferência de Maria armazena as mensagens na **caixa de mensagens** (mailbox) dela.
   - Quando Maria deseja ler suas mensagens, seu agente do usuário se conecta ao servidor e verifica quais mensagens estão armazenadas.

### *Protocolos Envolvidos*
- **SMTP (Simple Mail Transfer Protocol)**:
  - Definido pela **RFC 5321**, é responsável pela entrega da mensagem ao servidor de destino.
  - O servidor SMTP aguarda conexões, e quando um cliente se conecta, inicia a conversação informando se está pronto para receber mensagens.
  - Após receber a mensagem, o servidor confirma a recepção.

- **POP3 (Post Office Protocol version 3)**:
  - Definido pela **RFC 1939**, permite que o usuário baixe mensagens de sua caixa para o sistema local, podendo acessá-las offline.
  - Suporta download seletivo e exclusão de mensagens no servidor.

- **IMAP (Internet Message Access Protocol)**:
  - Definido pela **RFC 3501**, permite acesso às mensagens diretamente no servidor, sem necessidade de download.
  - Ideal para usuários que acessam e-mails de diferentes dispositivos, permitindo gerenciar várias caixas de correio.

### *Webmail*
Embora não seja um protocolo, o **webmail** é uma forma popular de acessar o correio eletrônico através de navegadores. Os usuários fazem login em uma página da web e podem acessar suas mensagens, semelhante ao funcionamento do IMAP.

## Serviço de Nomes DNS

### *Introdução ao DNS*
O **Domain Name System (DNS)** é um sistema crucial que facilita a comunicação na internet, traduzindo nomes de domínio em endereços IP. Isso evita a necessidade de lembrar endereços binários, que são difíceis de gerenciar e lembrar.

### *Serviços Oferecidos pelo DNS*
Além de mapear nomes de hospedeiros em endereços IP, o DNS fornece:

- **Identificação de servidores de correios eletrônicos**.
- **Apelidos para hospedeiros**.
- **Distribuição de carga**.
- **Descoberta de nomes de hospedeiros** (mapeamento reverso).

### *Estrutura do Espaço de Nomes*
O espaço de nomes do DNS é organizado hierarquicamente em **domínios**.

**Domínios Genéricos** - Indicam o tipo de organização:
- **.com** = comercial
- **.edu** = instituições educacionais
- **.int** = organizações internacionais
- **.org** = organizações sem fins lucrativos

**Domínios de Países** - Representam países específicos:
- **.br** = Brasil
- **.pt** = Portugal
- **.jp** = Japão
- **.ar** = Argentina

**Observações:**
- Os nomes de domínio não diferenciam maiúsculas de minúsculas (por exemplo, EDU e edu são o mesmo).
- Componentes de nomes podem ter até 63 caracteres; caminhos completos não podem ultrapassar 255 caracteres.

### *Resolução de Nomes*
O DNS é dividido em **zonas**, que são independentes e possuem:
- **Servidor de Nomes Principal:** Contém informações das zonas e repassa para servidores secundários.
- **Servidor de Nomes Secundário:** Assuma o controle em caso de falha do principal.

### *Componentes do DNS*
1. **Registros de Recursos:** Armazenados em um banco de dados distribuído.
2. **Servidores de Nomes DNS:** Mantêm zonas específicas.
3. **Solucionadores DNS:** Executados nos clientes.

### *Funcionamento da Resolução*
Quando um solucionador solicita a resolução de um nome, pode acontecer:

- **Servidor responsável:** Resolve o nome e devolve ao solucionador.
- **Resolução em cache:** O servidor não é responsável, mas tem a resolução em cache e a envia.
- **Busca necessária:** O servidor não tem a resolução em cache e precisa realizar uma busca.

### *Exemplo: Resolução do Nome `www.sus.gov.br`*
1. O solucionador solicita a resolução do nome ao servidor de nomes local (consulta recursiva).
2. O servidor local, sem informações em cache, consulta um servidor raiz para encontrar o servidor DNS de .br.
3. Realiza consultas iterativas até obter a resolução completa.

### *Prevenindo Sobrecargas*
Para evitar sobrecargas, os servidores devem negar consultas recursivas de clientes não autorizados, configurando quais clientes podem realizar essas consultas.