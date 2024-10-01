# **Conceitos gerais de padrões de projeto**

## Padrões de projeto

==Padrões de projeto são soluções para problemas recorrentes no desenvolvimento de software. Eles melhoram o código, facilitam sua manutenção, e criam um vocabulário comum entre as equipes.== Além disso, padrões ajudaram a padronizar o desenvolvimento de bibliotecas e frameworks, ==reduzindo o esforço necessário na criação de sistemas.==

==Ao serem utilizados, os padrões tornam o processo de evolução de sistemas existentes mais eficiente, proporcionando uma base estruturada que os desenvolvedores podem reutilizar.== Esses padrões surgiram como uma maneira de responder a perguntas mais complexas sobre a estruturação de sistemas, especialmente quando o desafio vai além da implementação de classes e interfaces.

Uma analogia ao jogo de xadrez é feita para explicar a evolução do conhecimento: ==assim como grandes enxadristas acumulam experiências para tomar melhores decisões, desenvolvedores experientes aplicam soluções conhecidas que funcionaram bem no passado.== Esse conhecimento foi registrado por quatro engenheiros de software no livro **"Design Patterns: Elements of Reusable Object-Oriented Software"** (1994), que apresentou 23 padrões de projeto. Esses engenheiros ficaram conhecidos como a "Gangue dos Quatro" (*GoF*), e os padrões descritos por eles se tornaram referência no desenvolvimento de software.

## Conhecendo padrões de projeto

Padrões de projeto (ou *design patterns*) são soluções nomeadas e estruturadas para problemas recorrentes em desenvolvimento de software. ==Embora muitas vezes descritos em termos de UML e associados ao paradigma orientado a objetos, os padrões de projeto podem ser aplicados em praticamente qualquer plataforma ou paradigma de programação, como o funcional e o reativo.==

==O uso de padrões permite adotar uma base de conhecimento amplamente testada e aceita no mercado, mas, como há várias famílias de padrões, é importante que o desenvolvedor saiba analisar e escolher o mais adequado para cada cenário.== Em alguns casos, o que é recomendado por um padrão pode ser desqualificado por outro, o que demanda experiência e discernimento.

### *O Que é um Padrão de Projeto?*
Um padrão de projeto descreve um problema recorrente e a estrutura fundamental de sua solução, definida por módulos e comunicações entre eles. ==Na orientação a objetos, isso se traduz em classes, interfaces e mecanismos de colaboração entre objetos.==

**Um padrão de projeto é composto por quatro elementos principais:**
1. **Nome**: Um nome descritivo para a solução.
2. **Problema**: O problema para o qual o padrão é uma solução.
3. **Solução**: A estrutura básica que resolve o problema.
4. **Consequências**: Vantagens e desvantagens em sua aplicação.

### *Vantagens do Uso de Padrões de Projeto*
- **Aumento de Produtividade**: Padrões fornecem um atalho para soluções bem-sucedidas, evitando a necessidade de experimentação e refinamento.
- **Reutilização de Código**: Promovem a reutilização com técnicas como delegação e composição, ao invés de depender da herança.
- **Linguagem Comum**: Facilitam a comunicação entre desenvolvedores, pois todos compartilham a mesma base de conhecimento.
- **Facilidade de Implementação**: Soluções testadas em múltiplos cenários permitem o uso eficiente em problemas similares, seguindo a “regra dos três” (um padrão só é válido se tiver sido utilizado em três contextos diferentes).

### *Desvantagens e Pontos de Atenção*
- **Curva de Aprendizado**: A quantidade de padrões existentes desde a década de 1990 é vasta, exigindo estudo aprofundado.
- **Dificuldade de Aplicação**: Identificar se um padrão é apropriado para um problema específico nem sempre é fácil e requer experiência.
- **Adaptação**: É necessário ajustar certos aspectos do padrão para que ele se adeque ao problema em questão.
- **Uso Inadequado**: Iniciantes tendem a utilizar padrões de maneira exagerada ou inadequada, comprometendo a qualidade do código.
- **Controvérsias**: Alguns padrões, como o *singleton*, são debatidos e considerados antipadrões por muitos desenvolvedores.

## Principais Padrões em Linhas Gerais

==Os padrões de projeto *GoF* (Gang of Four) têm papel fundamental no desenvolvimento de software, servindo como base para a criação de sistemas robustos e coerentes.==

**Eles são divididos em três categorias principais:**
1. **Padrões de Criação**
2. **Padrões Estruturais**
3. **Padrões Comportamentais**

Cada uma dessas categorias aborda diferentes aspectos da construção, organização e comportamento de objetos, facilitando a implementação de soluções consistentes e flexíveis.

### *Padrões de Criação*
Estes padrões têm como objetivo tornar a implementação independente da forma como os objetos são criados. ==Eles abstraem e encapsulam o processo de instanciamento, garantindo que o código de criação e o código de uso permaneçam desacoplados.==

**Principais Padrões de Criação:**
- **Abstract Factory**
- **Builder**
- **Factory Method**
- **Prototype**
- **Singleton**

### *Padrões Estruturais*
==Os padrões estruturais se concentram em compor classes e objetos para formar novas estruturas==, facilitando a criação de relacionamentos entre eles e a organização interna dos componentes do sistema.

### *Padrões Comportamentais*
==Os padrões comportamentais lidam com a comunicação e interação entre objetos==, garantindo que as responsabilidades sejam distribuídas de forma apropriada e que a comunicação seja eficiente.