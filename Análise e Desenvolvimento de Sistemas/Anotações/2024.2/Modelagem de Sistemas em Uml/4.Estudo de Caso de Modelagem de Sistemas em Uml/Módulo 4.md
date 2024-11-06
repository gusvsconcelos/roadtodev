# **Produzir o modelo de projeto para um estudo de caso de modelagem de sistemas em UML**

## Modelo de Interação  

Aqui são utilizados diagramas de **sequência** e **comunicação** para ilustrar a interação dinâmica entre objetos durante a execução de um caso de uso. No exemplo do estudo de caso, foi criado um diagrama de sequência para o caso de uso “Registrar Reserva”, detalhando a comunicação entre o cliente, a recepção, e o sistema. Ambos os diagramas são consistentes com o diagrama de classes e descrevem a troca de mensagens de forma sequencial.

- **Diagrama de Sequência**: Foca na ordem temporal das mensagens entre objetos.
- **Diagrama de Comunicação**: Foca nas relações entre os objetos, numerando as mensagens para indicar a ordem.

## Modelo de Classes de Projeto  

Esse modelo refina o **modelo de classes de análise**. São detalhadas as classes, incluindo métodos que foram representados nas mensagens dos diagramas de sequência. Também são aplicados conceitos como **associação bidirecional** (exemplo: Cliente ↔ Reserva) e **associação unidirecional** (exemplo: Reserva → Quarto).

- **Classes abstratas** (ex.: Pessoa) e o conceito de **polimorfismo** são introduzidos para organizar hierarquias genéricas.

## Modelo de Implementação  

O **diagrama de componentes** mostra como os diferentes pacotes e componentes do sistema se relacionam. No estudo de caso, cada aplicação (caso de uso empacotado) tem suas classes controladoras e views, com as classes do tipo model sendo acessadas por meio de uma interface comum.

## Modelo de Implantação  

Este modelo descreve os **nós de processamento físicos** em que o sistema será implantado. No estudo de caso, três nós computacionais são suficientes para a implantação do sistema, mostrando um nível elevado de abstração, mas podendo ser detalhado conforme a complexidade aumente.