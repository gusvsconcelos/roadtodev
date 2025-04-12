# **Conceitos básicos de softwares**

## 1. Conhecendo o software

**Software**: ==Conjunto de instruções que fazem o computador funcionar.==

**CPU (Unidade Central de Processamento)**: ==O "cérebro" do computador.==

Sempre que você usa um programa, está vendo um software em ação.

---
## 2. Representação e armazenamento das instruções em hardware

**Hardware**: ==Parte física do computador (CPU, memória, placa-mãe etc).==

**Código de máquina**: ==Instruções básicas representadas em 0 e 1 (binário).==

**Idioma de baixo nível**: Instruções simples que a CPU entende diretamente.

**Idioma de alto nível**: Instruções mais complexas e fáceis de entender para humanos.

### Compatibilidade entre famílias de CPUs

Cada tipo de CPU entende um código de máquina diferente.

- **Exemplo**: Software de PC não roda em celular porque as CPUs têm instruções diferentes.

### Compilação

O computador só entende baixo nível. Por isso, o **compilador** converte o código de alto nível em código de máquina.

> _Código-fonte → Compilador → Código de Máquina → Execução_

---
## 3. Software de código aberto

==Modelo onde o programa e seu código-fonte são distribuídos livremente.==

**Código aberto (software livre)**: ==Qualquer um pode ver, modificar e redistribuir.==

**Código fechado (proprietário)**: ==Somente o desenvolvedor tem acesso e pode alterar o código.==

---
## 4. O que é um programa?

>*Programa = executável com várias instruções.*

- É armazenado em um dispositivo persistente (HD, SSD, pendrive).

### Instruções básicas de um programa:

- **GOTO**: Muda a ordem da execução do código.  
    ==“Pule para outra linha e continue de lá.”==
- **IF**: Verifica uma condição.  
    ==Executa instruções diferentes dependendo se a condição for verdadeira ou falsa.==

==A CPU executa as instruções da RAM usando o ciclo busca-execução: busca uma instrução, executa, repete.==

### Como o programa vai parar na memória RAM?

1. As instruções são copiadas do armazenamento para a RAM.
2. A CPU lê essas instruções da RAM.
3. O ciclo busca-execução começa, rodando o programa rapidamente.