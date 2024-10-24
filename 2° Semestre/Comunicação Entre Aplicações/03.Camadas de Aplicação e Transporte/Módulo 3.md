# **Elementos da camada de transporte**

## Camada de Transporte na Internet

### *Função da Camada de Transporte*
A camada de transporte é crucial para garantir a entrega confiável de dados entre hospedeiros na internet, independentemente das redes físicas. Sua principal função é possibilitar que as aplicações se comuniquem, assegurando que mensagens ou fluxos de dados cheguem ao destino correto e na forma certa.

### *Objetivos da Camada de Transporte*
- **Serviço Confiável:** Promover a transferência de dados de forma confiável entre a origem e o destino.
- **Flexibilidade:** A aplicação pode decidir se deseja utilizar serviços orientados à conexão ou sem conexão.

### *Aspectos Fundamentais da Camada de Transporte*
- **Serviços à Camada de Aplicação:** A camada de transporte fornece serviços para a camada de aplicação imediatamente superior.
- **Arquitetura TCP/IP:** Na arquitetura TCP/IP, não existem as camadas de sessão e apresentação.

### *Tipos de Serviços de Transporte*
**Serviço Orientado à Conexão**
- **Confiável:** Realiza um controle rigoroso da conexão.
- **Três Fases:**
  1. Estabelecimento da conexão.
  2. Transferência de dados.
  3. Encerramento da conexão.
- **Verificação de Pacotes:** Identifica pacotes com erros ou não enviados, retransmitindo-os até garantir a entrega correta.

**Serviço Sem Conexão**
- **Não Confiável:** Não há controle sobre pacotes enviados.
- **Sem Recuperação:** Se um pacote se perder ou chegar com erro, nada será feito.
- **Desempenho:** É mais rápido, pois não exige verificações e retransmissões, ideal para aplicações onde a velocidade é mais crítica que a precisão.

### *Overhead*
- **Definição:** Refere-se à sobrecarga no sistema causada pelo processamento extra.
- **No Serviço Orientado à Conexão:** O overhead é gerado pela necessidade de verificar dados e retransmiti-los, o que pode afetar o desempenho.

### *Escolha do Serviço*
- **Aplicações que exigem confiabilidade:** Transferência de arquivos e e-mails, que precisam de dados corretos e livres de erros, optam pelo serviço orientado à conexão.
- **Aplicações onde a rapidez é prioridade:** Em serviços como telefonia em rede, um pequeno ruído é preferível a um atraso na transmissão, mesmo que isso signifique a perda de um pacote.

## Endereçamento dos Processos na Camada de Transporte

### *Importância do Endereçamento no Nível de Transporte*
Quando um programa faz uma solicitação a um servidor, ele precisa que a mensagem chegue à aplicação correta em um hospedeiro remoto. Como existem várias aplicações em um mesmo hospedeiro, é essencial identificar especificamente qual delas deve receber a mensagem. É aí que entra o **endereçamento no nível de transporte**!

### *Função do Endereçamento*
 **Identificação de Aplicações:** O endereçamento serve para indicar em qual aplicação os dados devem ser entregues, garantindo que o hospedeiro destino saiba exatamente para onde encaminhar as informações.

### *Endereço de Transporte*
Nos protocolos da camada de transporte, como o **TCP** e **UDP**, o endereço de transporte é conhecido como **porta**. Cada aplicação escuta em uma porta específica, permitindo que múltiplas aplicações coexistam no mesmo hospedeiro.

### *Como Funciona o Endereçamento*
**Associação de Endereços:** O hospedeiro origem pode saber qual porta o servidor no hospedeiro destino está utilizando por:
- Conhecimento prévio e estável do endereço (por exemplo, através de convenções estabelecidas).
- Distribuição de informações sobre endereços de serviço para novos usuários da rede.

**Servidores de Nomes:** Uma alternativa para identificar o endereço de transporte correspondente a um nome de serviço é usar um **servidor de nomes** ou **servidor de diretórios**. Neste modelo:
- A aplicação conecta-se ao servidor de nomes e envia uma mensagem com o nome do serviço.
- O servidor de nomes retorna o endereço de transporte apropriado.

### *Cabeçalhos da Camada de Transporte*
Os cabeçalhos (ou interfaces) da camada de transporte são fundamentais para a comunicação. Eles contêm informações essenciais que ajudam na entrega correta das mensagens entre as aplicações.

## Multiplexação e Demultiplexação na Camada de Transporte

### *O que são?*
- **Multiplexação**: É o processo de combinar dados de diferentes aplicações em um único fluxo de dados que será enviado pela rede. Isso permite que várias aplicações compartilhem o mesmo meio de comunicação.

- **Demultiplexação**: É a operação inversa. Quando os dados chegam ao hospedeiro de destino, a camada de transporte entrega os dados ao processo correto com base em informações contidas no cabeçalho dos segmentos.

### *Como Funciona?*
1. **Segmentos**: Os dados trocados entre as entidades de transporte são chamados de segmentos. Cada camada do modelo de rede tem seu próprio nome para os dados:
   - Camada de transporte: Segmentos
   - Camada de rede: Pacotes
   - Camada de enlace de dados: Quadros

2. **Portas**: Cada aplicação pode ter um ou mais endereços de transporte (portas) pelas quais os dados passam. Quando um segmento chega, a camada de transporte examina os campos de endereçamento no cabeçalho para identificar a porta receptora e direcionar o segmento a ela. Isso é a **demultiplexação**!

3. **No Hospedeiro Origem**: Durante a multiplexação, a camada de transporte:
   - Reúne porções de dados de diferentes portas.
   - Encapsula cada porção de dados com um cabeçalho que inclui informações para a demultiplexação.
   - Passa os segmentos para a camada de rede.

### *Exemplo Prático com Eduardo*
Vamos ver um exemplo usando o Eduardo, que está na internet fazendo várias coisas ao mesmo tempo:

- **Navegando na Web**: Eduardo acessa seu e-mail e faz download de arquivos com diferentes programas.
- **Protocolo de Transporte**: Ele está utilizando o **TCP** (Transmission Control Protocol).

**Como a Multiplexação Funciona para Eduardo?**
- Eduardo usa vários programas ao mesmo tempo, todos utilizando o TCP.
- Cada programa se registra em uma porta diferente:
  - Browser web: **11278**
  - Cliente de e-mail: **25786**
  - Programa de transferência de arquivos: **3709**

Quando o browser de Eduardo envia uma solicitação a um servidor web, o TCP inclui o número da porta **11278** na informação enviada. O servidor sabe, então, que deve responder enviando a resposta de volta para essa porta.

### *Resumo Final*
- **Multiplexação** = Juntar dados de várias aplicações para enviar pela rede.
- **Demultiplexação** = Separar os dados recebidos e entregá-los à aplicação correta.