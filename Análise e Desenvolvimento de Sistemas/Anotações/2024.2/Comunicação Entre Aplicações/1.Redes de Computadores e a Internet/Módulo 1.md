# **Conceitos básicos**

## O que é a Internet?

**Redes de Computadores:**
- ==**Definição:** Conjunto de módulos processadores interligados por um sistema de comunicação que possibilitam a troca de informações e o compartilhamento de recursos.==
  
**Internet:**
- **Definição:** Conjunto global de redes de computadores interligadas que ==operam utilizando os protocolos **TCP** (Transmission Control Protocol) e **IP** (Internet Protocol).==
- A internet conecta bilhões de dispositivos ao redor do mundo, mas vai além de ser apenas uma rede de redes.

**Componentes da Internet:**
A internet pode ser vista sob diferentes perspectivas. Uma delas é considerar os seus principais componentes de **hardware** e **software**, que se dividem em três grandes partes:
1. **Sistemas Finais:** Dispositivos de usuários, como smartphones e computadores.
2. **Núcleo da Rede:** Conjunto de roteadores e links de comunicação que encaminham os dados pela rede.
3. **Redes de Acesso:** Infraestrutura que conecta os sistemas finais ao núcleo da rede, como redes móveis e cabos de fibra óptica.

**Funcionamento:**
- A combinação desses três componentes permite que você utilize um dispositivo (ex: smartphone) para acessar serviços e aplicativos hospedados em qualquer lugar do mundo.
  
**Infraestrutura e Serviços:**
- A internet pode ser entendida também como uma **infraestrutura de redes** que fornece diversos **serviços**, como:
  - Definição de rotas do remetente até o destinatário.
  - Correção de erros de transmissão.
  - Evitar sobrecarga dos componentes.
  
Essa infraestrutura permite que os desenvolvedores se concentrem nas funcionalidades das suas aplicações, deixando para a internet a responsabilidade de entregar os dados corretamente entre origem e destino.

## O Entorno da Internet

**A Borda da Rede:**
- Os dispositivos que utilizamos para acessar a internet são chamados de **sistemas finais** ou **hosts**.
- Esses sistemas estão na periferia da internet e são onde as **aplicações de rede** são executadas.

**Categorias de Sistemas Finais:**
1. **Clientes:** 
   - Dispositivos como desktops, notebooks, smartphones e tablets.
   - Geralmente são usados por **usuários finais** para acessar a internet e utilizar serviços.
   
2. **Servidores:**
   - Máquinas mais robustas que armazenam e distribuem conteúdos como páginas web, vídeos, e-mails, entre outros.
   - O que define uma máquina como servidor não é seu **hardware**, mas sim o **software** que ela executa. Um servidor é responsável por **servir** alguma aplicação ou serviço a um cliente que faz uma requisição.

**Interação entre Sistemas Finais:**
- A comunicação entre os **clientes** e os **servidores** acontece constantemente, sendo a base do funcionamento de muitas aplicações de rede. 
- Por exemplo, quando você acessa uma página da web, seu dispositivo (cliente) faz uma requisição ao servidor, que responde com os dados da página.

## Redes de Acesso

**O que são redes de acesso?**
- Redes de acesso são a infraestrutura física que conecta **sistemas finais** (clientes/servidores) ao primeiro roteador no caminho até o núcleo da rede, conhecido como **roteador de borda**.
- Essencialmente, é o **meio físico** (ou enlace) que faz a ligação dos sistemas finais ao núcleo da internet.

**Tipos de Meios Físicos:**
1. **Meios Guiados:**
   - Redes **com fio**: Os sinais são propagados por cabos físicos.
     - Ex.: Cabo de **fibra ótica** (sinais luminosos), cabos de **par trançado de cobre** ou **cabos coaxiais** (sinais elétricos).

2. **Meios Não Guiados:**
   - Redes **wireless** (sem fio): Os sinais são transmitidos pelo ar, como em canais de rádio ou satélite.
     - Ex.: **Wi-Fi**, **telefonia celular** (sinais de 4G/5G), e **satélites** (em áreas rurais).

**Categorias de Redes de Acesso:**
1. **Redes Residenciais:**
   - **DSL (Linha Digital de Assinante):** Utiliza a linha telefônica existente, com ajuda de modems DSL.
   - **Cabo Coaxial:** Usa a infraestrutura de TV a cabo para fornecer acesso à internet.
   - **Fibra Ótica (FTTH - Fiber to the Home):** Conexão direta de fibra ótica até a residência, com maior velocidade e eficiência.
   - **Satélite:** Usado em áreas remotas onde outras tecnologias de acesso não estão disponíveis, embora com velocidades menores.
   - **Acesso Discado:** Conexão via linha telefônica, bastante comum até os anos 90 e início dos 2000, com modems de baixa velocidade.

2. **Redes Institucionais:**
   - Utilizam soluções semelhantes às residenciais, mas com foco em ambientes corporativos ou acadêmicos.
   - **LANs (Redes Locais):** Empregam principalmente o padrão **ethernet**, utilizando cabos metálicos ou redes sem fio **Wi-Fi** (padrão IEEE 802.11).
   - **Redes de Telefonia Celular:** Cada vez mais usadas como redes de acesso em ambientes corporativos e residenciais, com as tecnologias **4G/3G** e, mais recentemente, o **5G**, que oferece maior alcance e velocidades mais rápidas.
## O Núcleo da Rede

**O que é o núcleo da rede?**
- O núcleo da rede é composto por dispositivos como **roteadores**, **switches** e enlaces de alta velocidade, que interligam esses dispositivos.
- Ele é responsável por fornecer os possíveis caminhos que permitem a **interconexão** dos sistemas finais, conectando os bilhões de dispositivos ao redor do mundo.

**Organização do Núcleo:**
- O núcleo da rede é mantido por diversos **provedores de serviços de internet** (**ISPs - Internet Service Providers**), que oferecem conectividade aos usuários finais.
- Esses ISPs se interligam formando uma **rede de redes** altamente hierárquica e organizada.

**Tipos de ISPs:**
1. **ISPs de Acesso:**
   - Fornecem conexão diretamente aos usuários finais, permitindo o acesso à internet.
   
2. **ISPs de Trânsito:**
   - Responsáveis pela **interconexão entre ISPs**, mas não oferecem acesso direto aos usuários. Eles administram grandes infraestruturas como **cabos submarinos**.

**Hierarquia de ISPs:**
- **ISPs Locais:** Fornecem serviços em regiões menores (ex.: bairros ou pequenas cidades).
- **ISPs Regionais:** Conectam ISPs locais a uma área maior (ex.: estados ou regiões).
- **ISPs de Nível 1:** Têm alcance nacional e internacional, interconectando grandes redes ao redor do mundo.

**Ponto de Presença (PoP):**
- **PoP (Point of Presence):** Local físico com um ou mais roteadores onde ISPs clientes se conectam para acessar outras redes.
  
**Multi-homing:**
- **Multi-homing:** ISPs podem se conectar a dois ou mais ISPs para garantir **redundância** e maior confiabilidade. Por exemplo, um ISP local pode se conectar a dois ISPs regionais ou até a um ISP de nível 1.

**Emparelhamento entre ISPs:**
- **Emparelhamento (Peering):** ISPs no mesmo nível de hierarquia podem se conectar diretamente sem intermediários, reduzindo custos de tráfego. 
- ISPs de **nível 1** também costumam emparelhar suas redes sem custos entre si.
  
**Ponto de Troca de Internet (IXP - Internet Exchange Point):**
- **IXP:** Infraestrutura física, muitas vezes independente, que facilita o emparelhamento entre diferentes ISPs, permitindo a conexão direta entre eles.
- No Brasil, existe o **IX.br**, que facilita a troca de tráfego entre provedores de internet.

## A Rede como Serviço

**A internet como provedora de serviços:**
- A internet pode ser vista como uma **infraestrutura** que oferece diversos serviços para as **aplicações distribuídas**.
- Exemplos de aplicações: **Correio eletrônico**, **navegadores web**, **redes sociais**, **mensagens instantâneas**, **VoIP**, **streaming de vídeo**, **jogos online**, **P2P**, **login remoto**, entre outras.

**Execução das aplicações:**
- As **aplicações da internet** são executadas nos **sistemas finais**, ou seja, em dispositivos como computadores, smartphones e servidores.
- Os **comutadores no núcleo da rede** (roteadores e switches) não executam essas aplicações, apenas garantem que os dados trafeguem até o destino.

**Desenvolvimento de aplicações:**
- Para desenvolver essas aplicações, é necessário criar programas que rodem nos sistemas finais, utilizando linguagens de programação como **Java**, **C** ou **Python**.

**Interface de Programação de Aplicação (API):**
- As aplicações usam uma **API** específica para enviar dados pela rede, sem que o desenvolvedor precise se preocupar com detalhes técnicos como:
  - Entrega dos dados ao destino.
  - Correção de erros no trajeto.
  - Transformação dos bits em sinais elétricos, pulsos de luz ou ondas eletromagnéticas.

**Responsabilidade da infraestrutura de rede:**
- A **infraestrutura de rede** cuida de todo o processo de envio dos dados, desde a comunicação entre o **sistema operacional** dos dispositivos até a passagem pelos diversos componentes de rede (roteadores, switches, etc.).

**Curiosidade:**
- A **API** mais utilizada para a comunicação entre sistemas finais é chamada de **socket**.