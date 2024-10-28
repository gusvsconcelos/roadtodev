# **Conceitos Básicos**

A arquitetura de redes é organizada em camadas para facilitar a comunicação entre sistemas. Cada camada oferece serviços específicos para a camada imediatamente superior, o que permite dividir as tarefas de comunicação em diferentes funções especializadas. As principais camadas do modelo TCP/IP incluem **Física**, **Enlace**, **Rede**, **Transporte** e **Aplicação**.

## Elementos Fundamentais

### *Serviços*
Cada camada oferece uma função ou serviço específico para a camada acima. Por exemplo, a camada de transporte garante a entrega de dados para a camada de aplicação.

### *Protocolos*
 São regras que permitem a comunicação entre camadas equivalentes em dispositivos diferentes. Cada protocolo, como o HTTP na camada de aplicação, segue convenções estabelecidas para garantir a comunicação correta.
 
### *Interfaces*
 Definem os pontos de comunicação entre camadas adjacentes. Cada interface permite que uma camada consuma os serviços da camada abaixo, garantindo a troca vertical de dados.

## Camada de Aplicação

Esta camada é onde os serviços de rede são disponibilizados aos usuários, permitindo o desenvolvimento de aplicativos que acessam a rede. Exemplos de serviços incluem navegação na web, e-mail, transferência de arquivos e mensagens instantâneas. A camada de aplicação também é onde os desenvolvedores de redes atuam diretamente, sendo responsáveis por definir a interface e os protocolos que seus aplicativos usarão para se comunicar.

## Interface de Socket

Um socket é a interface entre a camada de aplicação e a de transporte, permitindo que um programa (cliente) se comunique com outro programa (servidor) em um dispositivo remoto. Sockets são implementados por meio de uma API (interface de programação de aplicativos) do sistema operacional, que permite o acesso a protocolos como UDP e TCP.

## Serviços da Camada de Transporte

Os dois principais serviços fornecidos pela camada de transporte são a multiplexação e o transporte confiável.

### *Multiplexação*
 Identifica pacotes de diferentes aplicações, permitindo que eles cheguem ao destino correto sem interferência entre si.
 
## *Transporte Confiável*
 TCP garante a entrega de dados na ordem correta e sem duplicação, enquanto UDP, apesar de mais rápido, não oferece garantias de confiabilidade.

## Endereçamento do Socket

Para que cliente e servidor se comuniquem corretamente, é necessário um endereço exclusivo que combina um endereço IP e um número de porta. **As portas são divididas em três intervalos:**

- ==**Portas Bem Conhecidas (0–1023)**, usadas por serviços essenciais (HTTP, FTP).==
- ==**Portas Registradas (1024–49151)**, destinadas a serviços específicos.==
- ==**Portas Dinâmicas (49152–65535)**, para conexões temporárias.==

## Primitivas de Sockets

A programação com sockets utiliza comandos conhecidos como primitivas, fundamentais para criar e gerenciar a comunicação entre dispositivos. As principais primitivas no modelo Berkeley incluem: `SOCKET`, `BIND`, `LISTEN`, `ACCEPT`, `CONNECT`, `SEND`, `RECEIVE` e `CLOSE`. O lado servidor, por exemplo, cria o socket, associa-o a uma porta e entra em modo de escuta com `LISTEN`, aguardando conexões com `ACCEPT`. Já o lado cliente, cria um socket e utiliza `CONNECT` para se conectar ao servidor.