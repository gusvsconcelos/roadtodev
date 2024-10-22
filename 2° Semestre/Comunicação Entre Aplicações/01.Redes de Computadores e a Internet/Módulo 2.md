# **Parâmetros de avaliação**
## Atraso em Redes de Comutação de Pacotes

As redes de computadores têm suas limitações, e é fundamental entender como funcionam os atrasos e a perda de pacotes para melhorar a transferência de dados.

### *Tipos de Atraso*
Ao enviar um pacote de um nó (como um sistema final ou um roteador) para outro, ele pode sofrer vários tipos de atraso ao longo do caminho. Aqui estão os principais:

1. **Atraso de Processamento Nodal**
   - Tempo que um dispositivo leva para analisar o cabeçalho do pacote e decidir para onde enviá-lo.

2. **Atraso de Fila**
   - Tempo que um pacote espera para ser transmitido. Se a fila estiver vazia, o atraso é zero. Se houver muitos pacotes esperando, o atraso pode ser considerável.

3. **Atraso de Transmissão**
   - Tempo necessário para enviar todos os bits do pacote para o enlace. Isso depende do tamanho do pacote e da taxa de transmissão do enlace, mas não da distância entre os dispositivos.

4. **Atraso de Propagação**
   - Tempo que leva para um bit percorrer a distância entre os dispositivos, variando conforme o meio físico (fibra ótica, cobre, etc.). Esse atraso está diretamente ligado à distância, mas não ao comprimento do pacote ou à taxa de transmissão.

### *Impacto nas Aplicações*
- **Aplicações de Tempo Real**: Jogos interativos e videoconferências são mais afetadas pelo atraso de propagação, pois exigem respostas rápidas.
  
- **Transferências de Arquivos**: Aplicações que lidam com grandes volumes de dados enfrentam desafios com o atraso de transmissão.

### *Efeito Jitter*
O **atraso de fila** pode variar bastante. Quando vários pacotes chegam ao mesmo tempo, o primeiro não sofre atraso, mas o último pode ter que esperar. Essa variação de atraso é conhecida como **jitter**, que pode impactar a qualidade de aplicações de streaming, pois os pacotes não chegam em intervalos regulares.

## Perda, Atraso Fim a Fim e Vazão

#### *Perda de Pacotes*
A perda de pacotes é um fator crucial que pode impactar o desempenho das aplicações. **Vamos entender como ela acontece:**
- **Baixa Intensidade de Tráfego**: Quando o tráfego está baixo, os pacotes chegam espaçados e têm menos chances de se acumularem na fila. Isso resulta em um atraso de fila próximo de zero, e todos os pacotes são processados sem perda.

- **Alta Intensidade de Tráfego**: Quando o tráfego se aproxima da capacidade máxima, períodos de congestionamento ocorrem, formando filas. Se a taxa de chegada de pacotes exceder a capacidade de transmissão do roteador, o buffer pode ficar cheio, levando à perda de pacotes.

- **Efeito da Perda**: Para aplicações que não toleram perda (como transferências de arquivos), um pacote perdido pode impactar a funcionalidade, exigindo retransmissões. Já as aplicações de streaming conseguem tolerar perdas; por exemplo, se alguns pacotes de vídeo forem perdidos, a ausência de alguns pixels é menos perceptível.

- **Infraestrutura da Rede**: A boa notícia é que, ao usar a API correta (como sockets), a rede pode lidar com a correção de perdas, permitindo que os desenvolvedores se concentrem na lógica das aplicações, enquanto a rede garante a entrega dos pacotes.

### *Atraso Fim a Fim*
Até agora, discutimos os atrasos em termos isolados entre os nós. Mas, ao considerar o caminho completo de um pacote, temos o **atraso fim a fim**, que é a soma de todos os atrasos que o pacote experimenta ao longo do caminho entre o sistema final de origem e o de destino.

- **Impacto dos Atrasos**: Se os atrasos de fila forem desprezíveis, a aplicação funciona bem. No entanto, atrasos significativos podem afetar aplicações sensíveis ao tempo, como videoconferências ou jogos online.

- **Ferramenta Traceroute**: Você pode usar o programa Traceroute para analisar os tempos de resposta entre roteadores ao longo do caminho. Ele permite visualizar os atrasos de ida e volta (RTT) e identificar gargalos na rede.

### *Vazão*
A **vazão** é outra métrica importante de desempenho. Para um arquivo transferido do hospedeiro A para o hospedeiro B, a vazão instantânea é a taxa (em bits/s) na qual o hospedeiro B está recebendo o arquivo.

- **Vazão Média**: A vazão média é calculada como a quantidade total de bits transferidos dividida pelo tempo total da transferência. 

- **Considerações de Aplicação**: Algumas aplicações, como telefonia via internet, preferem baixa latência e uma vazão instantânea acima de um certo nível. Outras, como transferências de arquivos, podem tolerar latências mais altas, mas buscam a maior vazão possível.

- **Fatores que Afetam a Vazão**: A vazão depende não só das taxas de transmissão dos enlaces, mas também do tráfego de outras aplicações. Por exemplo, um cabo submarino pode ter alta capacidade, mas se muitos outros usuários estiverem utilizando ao mesmo tempo, isso pode se tornar um gargalo.