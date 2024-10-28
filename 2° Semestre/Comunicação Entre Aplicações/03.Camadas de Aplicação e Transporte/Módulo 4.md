# **Serviços da camada de transporte**

## Protocolo UDP (User Datagram Protocol)

O **UDP** é um protocolo simples e rápido, ideal para situações em que a agilidade é mais importante do que a confiabilidade. Ele não oferece garantias de que os pacotes chegarão ao destino, nem retransmite pacotes perdidos, mas verifica erros usando uma soma de verificação (**CRC**).

### *Principais características do UDP*
- ==Não orientado à conexão.==
- ==Sem controle de fluxo ou retransmissão de pacotes.==
- ==Realiza multiplexação e demultiplexação com base nas portas.==

**Aplicações**: **DNS**, **SNMP**, **TFTP** e **RPC** são exemplos de sistemas que utilizam o UDP, onde a velocidade é crucial e pequenos erros são aceitáveis.

## Protocolo TCP (Transmission Control Protocol)

O **TCP**, ao contrário do UDP, é um protocolo confiável e orientado à conexão, utilizado em aplicações que precisam garantir a entrega correta e sequencial dos dados. Ele verifica se os pacotes chegam ao destino, retransmite pacotes perdidos e organiza os dados na ordem correta.

### *Principais características do TCP*
- ==Orientado à conexão, garantindo a entrega de dados sem erros.==
- ==Full-duplex: permite a troca simultânea de dados em ambas as direções.==
- ==Utiliza um modelo de **janela deslizante**, que permite o envio de múltiplos pacotes sem esperar a confirmação de cada um.==
  
### *Modelo de Serviço TCP*
- A comunicação é ponto a ponto, com controle de sequência e confirmação. O TCP permite o envio de grandes quantidades de dados de forma confiável, reorganizando os pacotes quando necessário.
  
### *Cabeçalho TCP*
Contém campos como:
- **Porta origem e destino**: identificam as aplicações.
- **Número de sequência**: organiza os pacotes.
- **Número de confirmação**: garante que os pacotes anteriores foram recebidos.
- **Flags**: incluem o **SYN** para iniciar uma conexão, o **FIN** para finalizá-la e o **ACK** para confirmar a recepção.

## Gerenciamento de Conexão TCP

Para estabelecer uma conexão, o TCP utiliza o **three-way handshake**. O processo segue três passos:
1. O cliente envia um segmento **SYN** para iniciar a conexão.
2. O servidor responde com **SYN-ACK**, confirmando que está pronto.
3. O cliente envia um **ACK** para finalizar o processo de estabelecimento da conexão.

Esse mecanismo garante que ambos os lados estejam prontos antes que os dados comecem a ser transmitidos, proporcionando uma comunicação estável e confiável.

## Portas

As portas são utilizadas para identificar aplicações em um sistema. Certas portas são bem conhecidas e reservadas para funções específicas, facilitando a comunicação entre clientes e servidores.

### *Portas comuns:*
- ==**80**: HTTP (navegação web).==
- ==**443**: HTTPS (navegação segura).==
- ==**25**: SMTP (envio de e-mails).==
- ==**53**: DNS (resolução de nomes).==