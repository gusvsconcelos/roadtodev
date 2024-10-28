# **Aplicação Prática de Sockets com TCP**

## Características do TCP

O TCP, ao contrário do UDP, oferece uma comunicação orientada à conexão, onde a troca de dados entre cliente e servidor só ocorre após uma conexão ser estabelecida. Este processo ocorre por meio do *Three-Way Handshake*, um mecanismo que assegura que ambos os lados estão prontos para enviar e receber dados. Com TCP, a transmissão de dados é garantida em ordem e sem duplicações, sendo ideal para aplicações que exigem confiabilidade, como transferência de arquivos e navegação web.

### *Conexão Orientada*
A comunicação ocorre após a confirmação de que cliente e servidor estão prontos para trocar dados, garantindo uma conexão estável.

### *Transmissão Contínua*
Os dados são enviados como um fluxo de bytes, sem divisão explícita em pacotes, permitindo que o receptor reordene o fluxo de forma confiável.

## Implementação de Servidor e Cliente TCP em Python

### *Servidor TCP*
Configura um socket, associa-o a uma porta específica com `bind()`, e entra em modo de escuta com `listen()`. Quando um cliente se conecta, o servidor utiliza `accept()` para estabelecer a comunicação, podendo então enviar e receber dados.

### *Cliente TCP*
Configura um socket e utiliza `connect()` para estabelecer a conexão com o servidor. Após a conexão, o cliente inicia a troca de dados com o servidor.

### *Exemplo de Código TCP*
No exemplo `tcp_exemplo.py`, cliente e servidor se comunicam de forma confiável. O servidor usa `listen()` para aguardar conexões e aceita um cliente por vez, enquanto o cliente utiliza `connect()` para estabelecer a conexão. A garantia de entrega de dados no TCP torna essa abordagem ideal para aplicações que não toleram perda de dados.