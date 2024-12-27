# **Conceitos básicos de softwares**

## Conhecendo o software

- **Software:** Software é o conjunto de funções executadas na programação de um computador.

- **CPU (Central Processing Unit):** Também chamada de processador, funciona como o "cérebro" do computador. ==É ela quem realmente executa o que chamamos de "instruções de código de máquina".==

Sempre que você baixa um programa ou vê um computador ligado, está presenciando algum software sendo executado.

---
## Representação e armazenamento das instruções em hardware

- **Código de máquina:** São instruções extremamente simples e constituídas apenas dos números zero e um, também conhecido como **código binário**.

- **Idioma de baixo nível:** Podemos pensar no conjunto de instruções de código de máquina que uma CPU é capaz de executar como sendo um idioma de baixo nível.

- **Idioma de alto nível:** São instruções muito mais complexas do que uma instrução de código de máquina individual que CPUs são capazes de executar.

- **Hardware:** É o termo usado para se referir à parte física do computador.

### *Compatibilidade entre diferentes famílias de CPUs*
Cada família de CPUs compatíveis possui seu próprio código de máquina especifico.

- **Exemplo:** Os programas de PC não rodam em smartphones, pois os idiomas de baixo nível dessas CPUs são incompatíveis.

### *Compilação*
==As instruções de alto nível são facilmente compreensíveis pelos humanos, mas os computadores não são capazes de executá-las.== O que ocorre, então, é que antes de ser executada, a instrução de alto nível será expandida em uma sequência - talvez cinco ou dez instruções de baixo nível (código de máquina).

- O compilador traduz linhas de código escritas pelo programador em instruções de código de máquina compreensíveis à CPU.

- Código-fonte **>>>** Compilador **>>>** Código de Máquina **>>>** Execução do programa.

---
## Software de código aberto

==Esse modelo de distribuição de software oferece o programa compilado e concede acesso ao seu código-fonte original==, permitindo que os usuários explorem, modifiquem e adaptem o software de acordo com suas necessidades e preferências.

- **Código aberto:** Também conhecido como "software livre". Você tem acesso ao código-fonte do programa e pode realizar modificações.

- **Código fechado:** Também conhecido como "software proprietário". Só o fornecedor do programa tem acesso ao código-fonte, e só ele é capaz de realizar ajustes e correções.

---
## O que é um programa?

Um programa é um arquivo que possui muitos bytes. Na maioria dos casos, esses bytes são apenas as instruções que compõem o programa, além de alguns ícones e fotos.

- Ao serem instalados, programas são colocados em um dispositivo de armazenamento persistente, como HD, SSD ou pendrive.

**Principais instruções que compõem um programa:**
- **GOTO:** Instrução para alterar a ordem de execução de instruções. ==Significa: vá para a linha indicada e siga executando o código a partir desse local.==

- **IF:** Instrução que testa alguma condição. ==É uma instrução que olhará para alguma condição; assim, se a condição for verdadeira, uma sequência de instruções especificas será executada, se for falsa, então executará uma sequência diferente.==

A CPU processa uma sequência de instruções presentes na memória RAM, esse processo, conhecido como *ciclo busca-execução*, envolve a CPU buscando e executando cada instrução uma após a outra.

### *Como o programa vai parar na memória RAM?*
- **Passo 1:** Cópia do bytes (ou seja, instruções) que compõem o programa no dispositivo de armazenamento persistente para uma área desocupada da memória RAM. Essa cópia é comumente chamada de carregar (*load*) o programa.

- **Passo 2:** Após o carregamento, a CPU já é capaz de realizar o ciclo busca-execução para rodar o programa.

- **Passo 3:** A CPU começa o processo de rodar/executar as instruções de forma incrivelmente rápida.