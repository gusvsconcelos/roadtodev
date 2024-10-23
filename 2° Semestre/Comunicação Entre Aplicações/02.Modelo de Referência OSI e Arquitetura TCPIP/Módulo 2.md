# **Camadas do modelo OSI**

## Modelo OSI

O **Modelo OSI (Open System Interconnection)** foi desenvolvido pela ISO na década de 1970 para criar uma referência que permitisse a comunicação entre sistemas distintos, independentemente de suas arquiteturas. Ele é mais um **modelo de referência** do que uma arquitetura de rede específica, já que não define os protocolos exatos a serem usados, mas sim o que cada camada deve fazer.

## Estrutura Geral do Modelo OSI

O Modelo OSI possui **sete camadas**, organizadas da seguinte forma, de cima para baixo:
1. **Aplicação**
2. **Apresentação**
3. **Sessão**
4. **Transporte**
5. **Rede**
6. **Enlace**
7. **Física**

Essas camadas formam uma pilha, onde cada uma é responsável por uma função específica no processo de transmissão de dados, seguindo os conceitos de **comunicação vertical** e **horizontal**, além do **encapsulamento**.

### *Subgrupos de Camadas do OSI*
O modelo pode ser dividido em três subgrupos principais:
1. **Camadas mais altas**:
   - Incluem as camadas de **Aplicação**, **Apresentação** e **Sessão**.
   - Responsáveis por dar suporte aos serviços de rede usados pelos usuários, como acessar dados e permitir a interoperabilidade entre sistemas diferentes.

2. **Camadas mais baixas**:
   - Englobam as camadas de **Rede**, **Enlace** e **Física**.
   - Essas camadas cuidam da movimentação dos dados entre dispositivos, garantindo que a comunicação ocorra fisicamente e de forma confiável.

3. **Camada de Transporte**:
   - A **camada de Transporte** faz a ligação entre as camadas superiores e inferiores, permitindo que os dados cheguem ao usuário de forma utilizável, além de garantir que a transmissão ocorra de forma eficiente e segura.
   
## Camadas de Aplicação, Apresentação e Sessão

### *1. Camada de Aplicação*
Essa é a camada mais próxima dos usuários e a que lida diretamente com as interações de rede que conhecemos e usamos no dia a dia. Exemplos de serviços disponíveis nesta camada incluem:

- **Serviços Web** (HTTP, HTTPS);
- **Correio eletrônico** (SMTP, IMAP);
- **Transferência de arquivos** (FTP, SFTP);
- **Streaming de áudio e vídeo** (Spotify, YouTube);
- **Compartilhamento de arquivos** (Google Drive, Dropbox).

Esses serviços são executados por processos em execução nos dispositivos dos usuários. É nessa camada que você interage com a rede, seja ao assistir um vídeo, enviar um e-mail ou acessar um site. 

### *2. Camada de Apresentação*
A camada de apresentação atua como uma **tradutora**. Ela garante que os dados possam ser compreendidos por sistemas heterogêneos (diferentes tipos de dispositivos e sistemas operacionais). Para isso, realiza funções importantes como:

- **Conversão de formatos** (garantindo que, por exemplo, um arquivo enviado de um Windows seja compreensível por um Linux);
- **Compressão de dados** (otimização do tamanho dos dados enviados para uma transmissão mais eficiente);
- **Criptografia** (protegendo os dados durante a comunicação).

A função dessa camada é garantir que os dados possam ser lidos e interpretados corretamente, independentemente da plataforma usada no envio ou no recebimento.

### *3. Camada de Sessão*
A camada de sessão é responsável por **organizar e gerenciar** a comunicação entre dois dispositivos, estabelecendo e mantendo sessões de comunicação. Suas funções principais são:

- **Controle de diálogo**: Gerencia quem fala e quem escuta, decidindo se a comunicação será **half duplex** (um por vez) ou **full duplex** (ambos ao mesmo tempo).
- **Sincronização**: Garante que, se a comunicação for interrompida, ela pode ser retomada de onde parou, sem perda de dados.

Essa camada garante que a comunicação seja contínua e confiável, especialmente em processos que requerem troca constante de informações, como chamadas de vídeo ou transferência de arquivos.

## Camadas de Transporte e Rede

### *1. Camada de Transporte*
A camada de transporte garante que os dados enviados cheguem **corretamente e na ordem certa** ao processo de destino. Ela cuida da **comunicação processo a processo**, assegurando que as mensagens que saem da camada de aplicação sejam entregues aos aplicativos certos, sem perda de dados ou duplicações. Para isso, desempenha algumas funções essenciais:

- **Controle de fluxo**: Garante que o remetente não envie dados mais rápido do que o destinatário pode processar.
- **Controle de erro**: Detecta e corrige erros que possam surgir durante a transmissão.
- **Multiplexação**: Gerencia múltiplos fluxos de dados simultâneos (vários aplicativos se comunicando pela rede ao mesmo tempo).

Se um arquivo é enviado por meio de um protocolo de transporte confiável, como o **TCP (Transmission Control Protocol)**, essa camada garante que, mesmo se um pedaço da mensagem se perder, ele será reenviado até chegar corretamente. Já em um protocolo não confiável, como o **UDP (User Datagram Protocol)**, essa garantia não existe, o que pode ser útil para transmissões que priorizam velocidade, como streaming de vídeos ao vivo.

### *2. Camada de Rede*
A camada de rede é o **cérebro do roteamento**. Ela é responsável por fazer com que os pacotes enviados pela camada de transporte cheguem de uma máquina de origem até a máquina de destino, mesmo que os dois dispositivos estejam em redes diferentes e tenham que atravessar vários intermediários (roteadores). Suas funções principais são:

- **Endereçamento lógico**: Utiliza endereços IP para identificar a origem e o destino dos dados. Isso permite que os pacotes possam ser roteados através de redes diferentes, até chegar no lugar certo.
- **Roteamento**: Define a melhor rota (caminho) para os dados chegarem ao destino, levando em conta fatores como congestionamento de rede, distância ou falhas.

Enquanto a camada de transporte se preocupa em garantir que os dados cheguem corretamente, a camada de rede se concentra em **encontrar o melhor caminho** para transportar esses dados de uma máquina para outra.

### *Resumo prático:*
- **Camada de Transporte**: Garante a comunicação **processo a processo**, confiabilidade e controle de fluxo de dados.
- **Camada de Rede**: Cuida do **roteamento** e endereçamento lógico para que os pacotes cheguem à máquina de destino, facilitando a comunicação **máquina a máquina**.

Essas camadas são essenciais para conectar redes e processos diferentes, permitindo que os dados fluam corretamente entre dispositivos.

## Camadas de Enlace e Física

### *1. Camada de Enlace*
A camada de enlace é a **ponte de comunicação entre dispositivos adjacentes** em uma rede, garantindo que os dados possam ser transmitidos de **nó a nó** de forma confiável. Diferente da camada de rede, que lida com o caminho completo dos dados de uma máquina de origem até uma de destino, a camada de enlace se concentra no transporte de dados entre dois dispositivos diretamente conectados ou próximos na rede (como dois roteadores consecutivos).

Algumas de suas funções principais incluem:
- **Controle de erro**: Corrige erros que possam ocorrer durante a transmissão dos dados pelo meio físico.
- **Controle de fluxo**: Garante que o receptor receba os dados na velocidade que pode processar.
- **Acesso ao meio**: Determina como vários dispositivos compartilharão o meio de transmissão para evitar colisões.

Essa camada trabalha com os **quadros (frames)**, que são unidades de dados encapsuladas pela camada de enlace. Assim, sua principal responsabilidade é garantir que esses quadros cheguem ao próximo dispositivo na rota, livres de erros.

Comparação:
- **Camada de Transporte**: Entrega **processo a processo**.
- **Camada de Enlace**: Entrega **nó a nó**.

### *2. Camada Física*
A camada física é a mais próxima do **hardware**, lidando com a **transmissão real dos bits** através de um meio físico, seja ele fibra ótica, cabo de cobre ou sinais sem fio. Sua responsabilidade é garantir que os bits sejam convertidos e transmitidos de forma adequada, com base nas características do meio físico.

Funções da camada física:
- **Representação de bits**: Define como os dados (0s e 1s) serão convertidos em sinais elétricos, ópticos ou de rádio para a transmissão.
- **Taxa de transmissão de dados**: Estabelece a velocidade com que os bits serão transmitidos pelo meio físico, como em Mbps (megabits por segundo).
- **Sincronização dos bits**: Garante que a transmissão e a recepção de dados estejam em sincronia para evitar perda de informações.
- **Topologia física**: Define como os dispositivos estão fisicamente conectados, seja em um esquema ponto a ponto, estrela, malha, entre outros.
- **Modo de transmissão**: Determina se a transmissão será **simplex** (um sentido), **half duplex** (ambos os sentidos, mas alternados), ou **full duplex** (ambos os sentidos simultaneamente).

### *Resumo das Funções:*
- **Camada de Enlace**: Cuida da **transmissão de dados entre dispositivos diretamente conectados**, corrigindo erros e controlando o fluxo de dados.
- **Camada Física**: Converte os **dados em sinais** e garante que sejam transmitidos pelo meio físico de forma eficiente e sincronizada.