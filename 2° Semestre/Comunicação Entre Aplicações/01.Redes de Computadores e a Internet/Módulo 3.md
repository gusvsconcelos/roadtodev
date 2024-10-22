# **Camadas de Protocolo e Modelos de Serviço**

## Arquitetura de Camadas

### *Protocólos de Comunicação*
1. **Definição de Protocolo**: Um protocolo é um conjunto de regras que governam a troca de mensagens entre entidades que se comunicam. Ele define o formato, a ordem das mensagens e as ações a serem realizadas durante a transmissão ou recebimento.

2. **Semelhança com Protocolos Humanos**: Assim como em interações humanas, onde cumprimentos e respostas seguem regras específicas (ex: dizer "oi" e esperar a mesma resposta), as entidades em uma rede devem seguir o mesmo protocolo para se comunicarem efetivamente. Por exemplo, um usuário deve enviar uma requisição e esperar uma resposta do servidor.

### *Estrutura em Camadas*
- **Organização dos Protocolos**: Para facilitar o desenvolvimento e a evolução das redes, os protocolos, junto com o hardware e o software que os implementam, são organizados em camadas. Essa estrutura em camadas ajuda a gerenciar a complexidade das comunicações em rede.

**Modelo de Serviço:**
- **Camadas e Serviços**: Cada protocolo opera em uma camada específica da arquitetura. **Cada camada:**
    - Oferece serviços à camada superior.
    - Utiliza os serviços da camada imediatamente inferior.
  - **Interfaces**: As camadas se comunicam entre si através de interfaces, que definem como as informações são trocadas.

### *Resumo*
A arquitetura de camadas permite que os protocolos sejam organizados de maneira a facilitar a comunicação entre diferentes entidades na rede, garantindo que as regras de troca de mensagens sejam seguidas e compreendidas. Essa estrutura é fundamental para o desenvolvimento e a manutenção das redes modernas, permitindo que novas tecnologias sejam integradas sem comprometer a funcionalidade existente.

## O Primeiro Modelo de Camadas

### *Modelo de Referência OSI*
No final dos anos 1970, a ISO (Organização Internacional para Padronização) lançou a ideia de organizar as redes de computadores em camadas. Isso resultou no **Modelo de Referência OSI** (Open Systems Interconnection), que ainda é utilizado como base para o entendimento das redes. O modelo é dividido em **sete camadas**, numeradas de cima para baixo:

1. **Camada de Aplicação**
2. **Camada de Apresentação**
3. **Camada de Sessão**
4. **Camada de Transporte**
5. **Camada de Rede**
6. **Camada de Enlace**
7. **Camada Física**

Embora o modelo OSI seja fundamental para o estudo das redes, ele não é amplamente utilizado na prática, pois não define protocolos específicos, mas sim os serviços que cada camada oferece.

### *Detalhamento das Camadas*
1. **Camada de Aplicação**:
   - **Função**: Implementa serviços de rede, como transferência de arquivos e envio de mensagens.
   - **Descrição**: Protocolos dessa camada permitem que aplicações em sistemas finais troquem informações através de mensagens.

2. **Camada de Apresentação**:
   - **Função**: Interpreta e traduz os dados trocados.
   - **Descrição**: Garante que sistemas diferentes possam comunicar-se, oferecendo serviços como compressão, criptografia e codificação de dados.

3. **Camada de Sessão**:
   - **Função**: Delimita e sincroniza a troca de dados.
   - **Descrição**: Permite a retomada de transferências (como downloads) a partir do último ponto de sincronização, se a conexão for interrompida.

4. **Camada de Transporte**:
   - **Função**: Garante a troca correta de dados entre sistemas finais.
   - **Descrição**: Encaminha mensagens (segmentos) da camada de aplicação, assegurando que não haja perda, mantendo a ordem e evitando sobrecarga.

5. **Camada de Rede**:
   - **Função**: Determina o caminho entre hospedeiros.
   - **Descrição**: Define endereços lógicos e realiza o roteamento. Os pacotes desta camada são conhecidos como datagramas.

6. **Camada de Enlace**:
   - **Função**: Encaminha pacotes (quadros) entre nós.
   - **Descrição**: Garante que os datagramas sejam entregues de forma confiável do nó atual para o próximo.

7. **Camada Física**:
   - **Função**: Transmite os bits de um nó para o próximo.
   - **Descrição**: Converte os bits em sinais adequados para o meio de transmissão (como fios de cobre ou fibra óptica).

### *Resumo*
O modelo OSI oferece uma estrutura clara para entender como as comunicações em rede são organizadas e as responsabilidades de cada camada. Essa arquitetura não só facilita o desenvolvimento de redes, mas também ajuda a padronizar a comunicação entre diferentes sistemas e tecnologias.

## Arquitetura TCP/IP (Arquitetura da Internet)

### *Visão Geral da Arquitetura*
Enquanto o modelo OSI é uma referência teórica, a **arquitetura TCP/IP** é a base prática das redes que utilizamos, conhecida como **arquitetura da internet**. Ela originalmente possui **quatro camadas**: aplicação, transporte, inter-rede e intrarrede. No entanto, para fins didáticos, costumamos apresentá-la como um modelo de **cinco camadas**: 

1. **Camada de Aplicação**
2. **Camada de Transporte**
3. **Camada de Rede**
4. **Camada de Enlace**
5. **Camada Física**

### *Diferenças entre OSI e TCP/IP*
- A **arquitetura TCP/IP** não possui as camadas de apresentação e sessão; suas funções são absorvidas pela camada de aplicação.
- O termo "modelo" (OSI) e "arquitetura" (TCP/IP) é utilizado de forma diferente: o OSI não define protocolos, enquanto a TCP/IP possui um conjunto de protocolos associados, conhecido como **pilha de protocolos TCP/IP**.

### *Detalhamento das Camadas TCP/IP*
1. **Camada de Aplicação**:
   - **Função**: Equivalente à camada de aplicação do modelo OSI, incorporando as funções de apresentação e sessão.
   - **Protocolos**: Inclui protocolos como **HTTP** (HyperText Transfer Protocol), **DNS** (Domain Name Server) e **SMTP** (Simple Mail Transfer Protocol).

2. **Camada de Transporte**:
   - **Responsabilidade**: Garante a confiabilidade das informações trocadas entre aplicações.
   - **Protocolos**:
     - **TCP (Transmission Control Protocol)**: Protocolo orientado à conexão que garante a entrega de mensagens, controle de fluxo e controle de congestionamento.
     - **UDP (User Datagram Protocol)**: Protocolo não orientado à conexão, que é econômico e não oferece controle de fluxo, sendo adequado para aplicações que toleram perda de pacotes, mas não atrasos.

3. **Camada de Rede**:
   - **Função**: Similar à camada de rede do modelo OSI, mas define o formato do endereço e as regras de encaminhamento por meio do protocolo **IP (Internet Protocol)**.

4. **Camada de Enlace**:
   - **Descrição**: Executa funções semelhantes às da camada de enlace do modelo OSI, embora não seja explicitamente definida na arquitetura da internet.
   - **Padrões**: Inclui tecnologias como **Ethernet**, **Wi-Fi** e **Bluetooth**.

5. **Camada Física**:
   - **Função**: Responsável pela transmissão física dos dados.

### *Resumo*
A arquitetura TCP/IP é fundamental para a operação da internet, definindo como as diferentes camadas interagem e se comunicam. Essa estrutura é prática e orientada a protocolos, permitindo a criação de um ambiente interconectado e eficiente.

## Encapsulamento

O **encapsulamento** é um conceito fundamental nas redes de computadores, que envolve a forma como os dados são empacotados e preparados para a transmissão entre diferentes camadas do modelo de protocolos. Aqui estão os principais pontos sobre o encapsulamento:

1. **Processo de Encapsulamento**:
   - Quando uma mensagem é criada na **camada de aplicação** de um sistema emissor, ela é passada para a **camada de transporte**.
   - A camada de transporte anexa um **cabeçalho** à mensagem. Esse cabeçalho contém informações importantes que serão usadas pela camada de transporte do sistema receptor.
   - A combinação da mensagem da camada de aplicação e do cabeçalho da camada de transporte forma a **Unidade de Dados de Protocolo (PDU)**, chamada de **segmento** na camada de transporte.

2. **Encadeamento de Camadas**:
   - O segmento é então enviado para a **camada de rede**, que adiciona seu próprio cabeçalho (incluindo endereços de origem e destino), criando um **datagrama** da camada de rede.
   - Esse datagrama é passado para a **camada de enlace**, que adiciona mais um cabeçalho e cria um **quadro** da camada de enlace.
   - Finalmente, na **camada física**, os dados são transmitidos como **bits** pelo meio físico (como cabos, fibras ópticas, etc.).

3. **Estrutura da PDU**:
   - Em cada camada, a PDU contém:
     - **Cabeçalho**: Informações sobre a camada correspondente.
     - **Carga útil**: Geralmente, a PDU da camada acima (o que está sendo encapsulado).

4. **Desencapsulamento**:
   - Quando os dados chegam ao sistema receptor, o processo de **desencapsulamento** começa. Isso significa que cada segmento deve ser reconstruído a partir dos datagramas que o compõem.
   - O sistema receptor vai “desempacotar” os dados, removendo os cabeçalhos conforme sobe nas camadas da pilha de protocolos.

5. **Caminho dos Dados**:
   - Os dados seguem um caminho específico ao serem enviados:
     - **Para baixo** na pilha de protocolos do sistema emissor.
     - **Para cima e para baixo** nas pilhas de protocolos de roteadores e comutadores no caminho (mas não implementam todas as camadas).
     - **Para cima** na pilha de protocolos do sistema receptor.

### *Exceções*
- Os **roteadores** da internet conseguem executar o protocolo IP (camada 3), enquanto **comutadores** de camada de enlace operam até a camada 2 (de enlace). 
- **Hospedeiros** (sistemas finais) implementam todas as cinco camadas da pilha de protocolos.

### *Resumo*
O encapsulamento é essencial para a comunicação eficiente e organizada nas redes de computadores. Ele garante que os dados sejam formatados corretamente para cada camada e possibilita a transmissão de informações de maneira controlada e sistemática.