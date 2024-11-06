# **Camadas da arquitetura TCP/IP**

## Arquitetura e Evolução do Protocolo TCP/IP

O TCP/IP (==Transmission Control Protocol/Internet Protocol==) é a base da comunicação na internet, sendo fundamental para o **desenvolvimento e expansão da rede global** como a conhecemos. Ele foi proposto em **1974** por Vinton Cerf e Robert Kahn como uma arquitetura que poderia **interligar diferentes redes de comunicação**, permitindo que sistemas diversos se conectassem de maneira eficiente e padronizada .

### *Estrutura de Camadas do TCP/IP*
A arquitetura TCP/IP se baseia em um modelo **de quatro camadas**:
1. **Aplicação**: Onde ocorrem as interações diretas entre o usuário e a rede, como o uso de e-mails, web, e transferência de arquivos. Protocolos conhecidos nessa camada incluem **HTTP, FTP, SMTP, DNS**.
2. ==**Transporte**: Responsável por garantir a comunicação **processo a processo**, com o controle de erros e a confiabilidade na entrega de dados. Aqui, temos o **TCP** (Transmission Control Protocol) e o **UDP** (User Datagram Protocol).==
3. **Internet**: Encarregada de fazer o roteamento dos pacotes de dados de origem a destino, utilizando o **IP** (Internet Protocol). Essa camada trata da comunicação entre **dispositivos em diferentes redes**.
4. **Acesso à Rede**: Une as funções de acesso físico e de enlace, sendo responsável por entregar pacotes de dados na rede local. Ela engloba tanto a **camada física** (como cabos, conexões sem fio) quanto a **camada de enlace**, que define como os dados serão transmitidos entre dois dispositivos diretamente conectados.

### *Comparação com o Modelo OSI*
Uma grande diferença entre o **modelo OSI** e a **arquitetura TCP/IP** é que o OSI foi desenvolvido com foco nas funcionalidades específicas de cada camada, enquanto o TCP/IP expandiu o conceito para incluir protocolos que funcionam de forma **independente e hierárquica**. A hierarquia no TCP/IP permite que protocolos de nível superior (como HTTP) **dependam dos serviços dos protocolos de nível inferior** (como TCP e IP) sem que estejam rigidamente acoplados a eles.

### *Evolução do TCP/IP*
Desde sua criação, o TCP/IP evoluiu constantemente, com a adição de novos protocolos e a adaptação às necessidades da internet moderna. Grande parte dessa evolução foi coordenada pela **IETF (Internet Engineering Task Force)**, uma comunidade internacional aberta composta por designers de redes, operadores e pesquisadores.

Essa estrutura flexível e em constante evolução permitiu que a internet crescesse de maneira exponencial, sendo hoje o padrão de comunicação global.

### *Considerações*
O **TCP/IP** se destacou por ser mais prático e escalável em comparação ao modelo OSI, e acabou se tornando a base real para a internet. A flexibilidade na adição de novos protocolos e sua arquitetura menos rígida foram alguns dos principais fatores que levaram ao seu sucesso.

## Camadas da Arquitetura TCP/IP e seus Principais Protocolos

A arquitetura TCP/IP é composta por **quatro camadas** que desempenham funções específicas e utilizam uma variedade de protocolos para comunicação eficiente.

### *Camada de Aplicação*
Esta camada **engloba as funções das camadas de aplicação, apresentação e sessão** do modelo OSI. É onde as interações entre usuários e serviços ocorrem diretamente. Aqui, são definidos os protocolos que permitem o acesso a serviços na internet, como navegação web, e-mail e DNS.

| **Serviço**                         | **Protocolo**   |
| ----------------------------------- | --------------- |
| Web                                 | HTTP, HTTPS     |
| Correio Eletrônico                  | SMTP, POP, IMAP |
| Serviço de Nomes (DNS)              | DNS             |
| Transferência de Arquivos           | FTP, TFTP       |
| Áudio e Vídeo em Tempo Real         | RTP             |
| Configuração Automática de Estações | DHCP            |

Esses serviços operam em duas principais arquiteturas:
- **Cliente-servidor**: Um cliente solicita um serviço de um servidor (ex.: navegador acessando um site).
- **P2P (Peer-to-peer)**: Usuários trocam dados diretamente, sem um servidor central (ex.: compartilhamento de arquivos).

### *Camada de Transporte*
A camada de transporte, como no modelo OSI, **garante a entrega confiável de dados de processo a processo. No TCP/IP, há dois protocolos principais:**
- **TCP (Transmission Control Protocol)**: Protocolo orientado à conexão, que oferece controle de erro, fluxo, e garante que os dados cheguem ao destino em ordem e sem erros. Usado em aplicações que necessitam de confiabilidade, como downloads de arquivos.
- **UDP (User Datagram Protocol)**: Protocolo **não orientado à conexão**. Não garante a entrega dos dados, mas é utilizado em situações onde a **baixa latência** é mais importante que a confiabilidade, como em transmissões de áudio e vídeo em tempo real.

### *Camada de Internet (ou Rede)*
A camada de Internet é responsável por fazer com que os dados alcancem o destino, independentemente do caminho percorrido. O protocolo mais importante aqui é o **IP (Internet Protocol)**, que existe em duas versões:
- **IPv4**: Endereçamento mais comum, com endereços de 32 bits.
- **IPv6**: Endereçamento mais recente, com endereços de 128 bits, criado para suprir a demanda crescente por endereços IP.

Essa camada oferece um serviço de **"melhor esforço"**, ou seja, não há garantias de que os dados chegarão, ou que chegarão na ordem correta.

Outros protocolos auxiliares da camada Internet incluem:
- **ICMP (Internet Control Message Protocol)**: Usado para enviar mensagens de erro e informações operacionais.
- **ARP (Address Resolution Protocol)**: Faz a tradução de endereços IP para endereços físicos (MAC).
- **IGMP (Internet Group Management Protocol)**: Facilita a comunicação multicast, permitindo o envio de dados para múltiplos destinatários.

### *Camada de Acesso à Rede*
Essa camada **não foi rigidamente definida** na arquitetura TCP/IP, e basicamente qualquer tecnologia que conecte dispositivos a uma rede pode ser usada. Ela combina as funções das camadas de enlace e física do modelo OSI. 

- **Ethernet** e **Wi-Fi** são exemplos de padrões amplamente utilizados, definidos pela **IEEE 802**.
  
Embora a arquitetura TCP/IP não tenha uma camada de "acesso à rede" detalhada, o papel desempenhado aqui é essencial para a **conectividade física** dos dispositivos.

## Evolução dos Protocolos TCP/IP

Os protocolos evoluíram significativamente desde a criação do TCP/IP. No início, as aplicações eram textuais e de baixo volume de dados, como o serviço Web desenvolvido por **Tim Berners-Lee**. Hoje, os protocolos oferecem **suporte a tráfego multimídia**, **transações financeiras** e **segurança** (como o HTTPS), tornando a internet robusta o suficiente para as diversas aplicações modernas, como **streaming de vídeo** e **sistemas complexos** como ERPs e CRMs.

## Resumo

- **Camada de Aplicação**: Interage diretamente com o usuário e gerencia serviços como Web, e-mail e DNS.
- **Camada de Transporte**: Garante a entrega de dados processo a processo, com protocolos como TCP e UDP.
- **Camada de Internet**: Roteia os dados para o destino, com o protocolo IP (IPv4 e IPv6) e auxiliares como ARP e ICMP.
- **Camada de Acesso à Rede**: Define como os dados serão transmitidos fisicamente entre os dispositivos, usando padrões como Ethernet e Wi-Fi.