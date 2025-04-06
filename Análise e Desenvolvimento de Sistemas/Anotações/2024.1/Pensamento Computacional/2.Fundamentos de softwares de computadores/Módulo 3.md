# **Linguagens de Programação**

## 1. Conceito: Linguagens de programação

==Uma linguagem de programação é um sistema de comunicação usado para criar instruções que um computador pode entender e executar.==

### Principais Características de uma Linguagem de Programação

**Sintaxe**: Conjunto de regras que define como o código deve ser escrito e estruturado.

**Semântica**: O significado das instruções e comandos definidos pela sintaxe.

**Abstração**: As linguagens permitem que os desenvolvedores se concentrem em tarefas específicas sem precisar lidar diretamente com o hardware.

---
## 2. Classificação das Linguagens de Programação

### Linguagens de Baixo Nível

- ==Mais próximas do hardware.==
- **Exemplo**: Assembly, Linguagem de Máquina.
- **Características**: Rápidas e eficientes, mas difíceis de programar.

### Linguagens de Alto Nível

- ==Mais próximas da linguagem humana.==
- **Exemplo**: Python, Java, C++, JavaScript.
- **Características**: Mais fáceis de aprender e usar, mas menos eficientes em termos de desempenho bruto.

### Paradigmas de Programação

- **Imperativo**: ==Baseado em comandos sequenciais== (Ex.: C, Python).
- **Orientado a Objetos**: ==Organizado em torno de objetos e classes== (Ex.: Java, C#).
- **Funcional**: ==Foca em funções matemáticas e imutabilidade== (Ex.: Haskell, Scala).
- **Declarativo**: ==Foco em "o que fazer" em vez de "como fazer"== (Ex.: SQL, Prolog).

### Exemplos de Linguagens Populares

- **Python**: Simples e versátil, usado em ciência de dados, web, automação.
- **JavaScript**: Principalmente usado no desenvolvimento web.
- **Java**: Muito usado em aplicativos empresariais e Android.
- **C**: Base para muitas outras linguagens, usada em sistemas embarcados e aplicações de alto desempenho.

---
## 3. Linguagens Compiladas, Interpretadas e Just-in-Time

Essas três categorias se referem a como o código-fonte de um programa é traduzido para o código de máquina que o computador pode entender e executar.

### Linguagens Compiladas

 ==O código-fonte é transformado (compilado) em código de máquina antes de ser executado.== Essa tradução é feita por um **compilador**.
 
- **Exemplos**: C, C++, Rust, Go.

#### *Características*

- O programa gerado é um arquivo executável independente.
- ==Execução geralmente mais rápida, pois o código já está traduzido para a linguagem da máquina.==
- Menor flexibilidade para mudanças durante a execução.
  
#### *Vantagens*

- Alto desempenho.
- Não depende de um interpretador durante a execução.
#### *Desvantagens*

- O processo de compilação pode ser lento.
- Não é fácil depurar ou alterar sem recompilar.

### Linguagens Interpretadas

==O código-fonte é traduzido e executado linha por linha por um *interpretador* em tempo de execução.==

- **Exemplos**: Python, Ruby, JavaScript.

#### *Características*

- Não há um arquivo executável pré-compilado.
- ==Mais lento em execução, já que a tradução acontece durante o uso.==
- Maior flexibilidade para mudanças no código.

#### *Vantagens*

- Fácil de testar e depurar.
- Multiplataforma sem necessidade de recompilação.

#### *Desvantagens*

- Desempenho geralmente inferior ao de linguagens compiladas.
- Requer um interpretador instalado no ambiente de execução.

### Compilação Just-in-Time (JIT)

==Uma combinação dos dois métodos anteriores. O código é compilado em tempo de execução==, gerando código de máquina "sob demanda".

- **Exemplos**: Java (com a JVM), C# (com o .NET CLR), Kotlin.

#### *Características*

- ==O código é inicialmente convertido em um formato intermediário (bytecode) e depois, no momento da execução, o bytecode é compilado em código de máquina.==
- Combina a portabilidade de linguagens interpretadas com o desempenho das compiladas.

#### *Vantagens*

- Melhor desempenho em relação às linguagens interpretadas puras.
- Otimizações específicas para o hardware no momento da execução.

#### *Desvantagens*

- Introduz uma sobrecarga durante a execução inicial.
- Depende de uma máquina virtual ou ambiente JIT (ex.: JVM, CLR).