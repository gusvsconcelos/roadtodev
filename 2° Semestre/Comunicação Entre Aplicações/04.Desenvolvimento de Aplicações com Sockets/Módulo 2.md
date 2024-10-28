# **Aplicação Prática de Sockets com UDP**

Neste módulo, abordamos a implementação de sockets com o protocolo UDP em Python usando a biblioteca padrão `socket`. O protocolo UDP não possui mecanismos de confirmação de entrega ou retransmissão de pacotes, sendo ideal para aplicações que priorizam velocidade e baixa latência, como jogos em tempo real ou streaming de vídeo.

## Implementação de Servidor e Cliente UDP

### *Servidor UDP*
Cria um socket configurado para UDP e utiliza `bind()` para associá-lo a um endereço IP e porta específicos. Após a configuração, o servidor entra em um loop para receber mensagens enviadas por clientes e responder de forma apropriada.

### *Cliente UDP*
Cria um socket e envia mensagens para o servidor especificado. Após enviar, ele aguarda uma resposta do servidor. Em UDP, o cliente e o servidor não estabelecem uma conexão antes da troca de dados, o que torna o processo mais rápido, porém menos confiável.

## Exemplo de Código UDP

O exemplo em `udp_local.py` demonstra a comunicação entre servidor e cliente em um ambiente de loopback, onde cliente e servidor estão na mesma máquina. Esta abordagem simplificada é prática para testar o envio e o recebimento de mensagens sem as limitações de uma rede externa.