# **Padrões GRASP**

**GRASP** (General Responsibility Assignment Software Patterns) foi definido por **Craig Larman** no livro **Applying UML and Patterns** e ==se refere a um conjunto de padrões gerais para atribuição de responsabilidades em software orientado a objetos.==

Ao contrário dos padrões GoF, que abordam problemas específicos, ==os padrões GRASP se concentram em princípios gerais de design.==

**Comparação:**
- **Padrões GoF:** Focados em problemas específicos de projeto de software.
- **Padrões GRASP:** Princípios gerais de design para software orientado a objetos.

**Neste módulo, são introduzidos seis padrões GRASP:**
1. **Especialista**
2. **Criador**
3. **Baixo Acoplamento**
4. **Alta Coesão**
5. **Controlador**
6. **Polimorfismo**

*O foco deste módulo é o padrão **Especialista**, que trata da atribuição de responsabilidades aos objetos no sistema.*

## Especialista
### *Problema*
Quando desenvolvemos um sistema orientado a objetos, uma das principais tarefas é definir as responsabilidades de cada classe e as interações necessárias entre os objetos para garantir que as funcionalidades desejadas sejam cumpridas com uma estrutura de fácil entendimento, manutenção e extensão.

### *Solução*
Atribua a responsabilidade ao especialista — ao módulo que tem o conhecimento necessário para realizar a tarefa. Por exemplo, ao desenvolver um site de vendas online, a classe `Pedido` deve ter a responsabilidade de calcular o valor total do pedido, pois ela detém as informações dos itens que o compõem.

### *Exemplo*
**Em um site de vendas, considere as seguintes classes:**
- **Pedido**: responsável por gerenciar os itens do pedido.
- **Item do Pedido**: conhece a quantidade e o preço unitário do produto associado.

Neste cenário, o valor total do pedido é a soma dos valores de cada item. Portanto, a operação `obterValorTotal` deve ser definida na classe `Pedido`, enquanto a operação `obterValor` (cálculo do valor de cada item) deve estar na classe `Item do Pedido`.

### *Consequências*
==Quando o padrão Especialista não é seguido, surge o antipadrão conhecido como **God Class**, que concentra as funcionalidades em uma única classe==, enquanto as outras classes apenas fornecem dados por meio de getters e setters.

==Esse design gera classes chamadas "idiotas", que não possuem responsabilidades próprias, e concentra toda a lógica em uma classe de controle ou serviço.==

Por outro lado, em algumas situações, seguir rigorosamente o padrão Especialista pode comprometer conceitos como coesão e acoplamento. Por exemplo, atribuir a responsabilidade de armazenamento dos dados a uma classe `Pedido` fere o princípio de coesão, pois mistura responsabilidades de negócio com tecnologia de armazenamento (e.g., SQL, NoSQL). ==Isso acopla a classe de negócio com a tecnologia de armazenamento, tornando-a suscetível a alterações em ambos os contextos.==

### *Considerações Finais*
O padrão Especialista é uma diretriz útil para atribuição de responsabilidades, mas ==é necessário ter cuidado ao aplicá-lo, garantindo que o design do sistema permaneça coeso e com baixo acoplamento.==

## Criador e Baixo Acoplamento

Os padrões **GRASP** se concentram em definir as responsabilidades de cada componente de software para facilitar o design orientado a objetos. Neste contexto, ==os padrões **Criador** e **Baixo Acoplamento** são apresentados como guias para tornar a instanciação de objetos e a relação entre módulos mais eficiente e flexível.==

### *Criador*
#### **Problema:**
A instanciação de objetos é uma das operações mais comuns em programas orientados a objetos. ==Entretanto, criar objetos indiscriminadamente por todo o sistema gera uma estrutura com alto acoplamento e pouca flexibilidade, dificultando modificações e manutenções futuras.==

A pergunta que este padrão busca responder é: **quem deve ser responsável pela criação de um objeto de determinada classe?**

#### **Solução:**
**A responsabilidade de criar um objeto deve ser atribuída a uma classe que:**
- Contém as instâncias desse objeto (como um agregado).
- Possui as informações necessárias para inicializar uma nova instância.

Por exemplo, em um site de vendas, a classe `Pedido` deve ser responsável por criar instâncias de `ItemDoPedido`, pois `Pedido` gerencia e conhece os dados necessários para inicializar cada item do pedido.

#### **Consequências:**
- **Indicado:** para criar instâncias que formam parte de um agregado, promovendo baixo acoplamento e organização.
- **Não indicado:** para criação condicional de instâncias em uma família de classes similares, onde pode ser mais adequado usar um padrão como Factory.

### *Baixo Acoplamento*
#### **Problema:**
O **acoplamento** refere-se ao grau de dependência de um módulo em relação a outros módulos no sistema. **Um alto acoplamento pode gerar:**
- Propagação de mudanças, complicando a manutenção.
- Dificuldade para entender o módulo isoladamente.
- Baixa reutilização do módulo em outros contextos.

A pergunta que este padrão tenta responder é: *como definir as relações de dependência entre as classes de um sistema para manter o acoplamento baixo, minimizar o impacto de mudanças e facilitar o reuso?*

#### **Solução:**
Distribuir as responsabilidades para garantir baixo acoplamento entre os módulos. ==Isso pode ser feito ao definir relações de dependência baseadas em abstrações (interfaces) e não em implementações concretas.==

**Exemplo de contraexemplo:** uma situação com alto acoplamento seria calcular o valor de um pedido na classe `Pedido` acessando diretamente os detalhes de cada `Produto` no pedido. Isso criaria um acoplamento excessivo entre `Pedido` e `Produto`, que pode ser evitado delegando esse cálculo à classe `ItemDoPedido`, como recomendado pelo padrão Especialista.

#### **Consequências:**
Baixo acoplamento é um princípio fundamental para estruturar software, mas deve ser aplicado com equilíbrio para não gerar soluções excessivamente complexas. ==Em geral, é preferível manter classes de domínio isoladas de tecnologias como persistência e GUI.==

### *Considerações Finais*
- **Padrão Criador:** define a classe responsável por criar outras instâncias, promovendo um design mais organizado e de menor acoplamento.
- **Padrão Baixo Acoplamento:** minimiza dependências desnecessárias entre módulos, facilitando a manutenção e a evolução do sistema.

## Alta Coesão

### *Definição*
O padrão **Alta Coesão** trata da forma como as responsabilidades de um módulo (seja ele um método, classe, pacote ou subsistema) são distribuídas, visando garantir que todas as funcionalidades estejam relacionadas a um propósito comum. Isso torna o sistema mais organizado, fácil de entender, manter e evoluir.

==A **coesão** mede a relação interna de um módulo em termos de alinhamento e proximidade entre suas funcionalidades.== Um módulo com alta coesão realiza um conjunto de operações fortemente relacionadas, enquanto um módulo com baixa coesão realiza várias operações desconectadas entre si, o que gera confusão e aumenta a complexidade do sistema.

#### **Problema**
Baixa coesão implica em módulos com diversas responsabilidades mal relacionadas, **o que pode levar a:**
- **Dificuldade de compreensão**: O comportamento do módulo não é claro e é difícil de entender.
- **Reuso limitado**: As funcionalidades são muito específicas ou dispersas, dificultando o reuso em outros contextos.
- **Alta sensibilidade a mudanças**: Uma alteração em um aspecto do módulo pode exigir mudanças em outras funcionalidades não diretamente relacionadas.

A pergunta que o padrão Alta Coesão busca responder é: *como definir as responsabilidades dos módulos de forma que a complexidade resultante seja gerenciável?*

#### **Solução**
A solução é **estruturar módulos com alta coesão**, ou seja, agrupar elementos (atributos, métodos, classes) que compartilhem o mesmo propósito e que estejam focados em uma única responsabilidade bem definida. **Isso pode ser aplicado em diferentes níveis:**
- **Método**: Um método deve conter instruções que estejam relacionadas para cumprir uma única funcionalidade.
- **Classe**: A classe deve agrupar atributos e operações que descrevam um comportamento específico e coeso.
- **Pacote**: Deve reunir classes e interfaces relacionadas a um mesmo domínio funcional.
- **Subsistema**: Deve integrar pacotes que cumpram um objetivo comum mais amplo.

Por exemplo, em Java, o pacote `java.io` agrupa classes voltadas para operações de entrada e saída (I/O), cada uma com responsabilidades claras, como `FileInputStream` (para leitura de arquivos binários) e `FileReader` (para leitura de arquivos de texto).

#### **Consequências**
**Seguir o padrão de alta coesão proporciona diversas vantagens:**
1. **Flexibilidade**: Modificações no módulo são mais previsíveis, pois as responsabilidades são claras.
2. **Reusabilidade**: Um módulo coeso pode ser facilmente reutilizado, pois possui uma funcionalidade bem definida.
3. **Facilidade de manutenção**: A mudança em um comportamento é mais simples de gerenciar, e os efeitos colaterais são minimizados.
4. **Baixo acoplamento**: Alta coesão tende a gerar baixo acoplamento, pois um módulo bem estruturado depende menos de outros módulos para cumprir suas funcionalidades.

### *Considerações Finais*
O padrão **Alta Coesão** é uma prática fundamental em projetos orientados a objetos, especialmente quando combinado com o padrão **Baixo Acoplamento**. ==A ideia é criar módulos que sejam coesos e independentes, promovendo um design mais claro e robusto.==

Esses princípios são particularmente importantes em sistemas distribuídos, onde é necessário um equilíbrio para evitar a comunicação excessiva entre módulos, respeitando o princípio de minimizar as chamadas entre processos, garantindo desempenho e eficiência.

Em resumo, a aplicação de alta coesão assegura um sistema modular, de fácil manutenção e adaptabilidade, além de proporcionar um entendimento mais claro das responsabilidades e do comportamento de cada módulo no sistema.

## Controlador

### *Definição*
O padrão **Controlador** do GRASP estabelece uma classe responsável por gerenciar eventos e coordenar a execução das operações apropriadas. ==Seu principal objetivo é centralizar a lógica de controle e processamento de eventos gerados por atores externos (como o usuário) para manter a estrutura do sistema organizada e coesa.==

Assim como um maestro coordena os músicos de uma orquestra, um controlador coordena a interação entre diferentes classes e módulos, delegando a execução de cada funcionalidade aos componentes adequados.

#### **Problema**
Em sistemas de software, é comum que eventos, como cliques em botões, submissões de formulários ou solicitações de APIs, desencadeiem processos que precisam ser tratados pelo sistema. A questão central é: *quem deve ser responsável por capturar e processar esses eventos?*

Caso essa responsabilidade seja mal atribuída, o resultado será um código de difícil manutenção e evolução, pois a lógica de controle e o comportamento do sistema estarão dispersos em várias classes ou, ainda pior, concentrados em um único módulo pouco coeso.

#### **Solução**
A solução consiste em atribuir a responsabilidade de receber eventos e coordenar a execução das operações a uma classe **controladora**. **Essa classe pode ser implementada de duas maneiras principais:**
1. **Controlador Fachada**: 
   - Utilizado em sistemas com um número reduzido de eventos.
   - A classe controladora representa todo o sistema ou um subsistema específico.
   - Centraliza o controle, facilitando a organização das funcionalidades.

2. **Controlador de Caso de Uso**:
   - Utilizado quando há vários eventos associados a um mesmo fluxo de trabalho ou funcionalidade específica.
   - A classe controladora é criada com base no nome do caso de uso, como `ProcessadorFechamentoPedido` ou `ControladorTransferencia`.
   - Esse tipo de controlador coordena eventos dentro do contexto de um caso de uso, garantindo alta coesão e baixa complexidade no tratamento de cada funcionalidade.

Em um sistema *MVC* (Model-View-Controller), por exemplo, o **Controlador** é responsável por receber as solicitações vindas da interface de usuário (**View**), interagir com a camada de modelo (**Model**) para realizar as operações necessárias e, por fim, atualizar a interface conforme necessário. Frameworks como o **Spring** fazem uso do padrão Controlador através de anotações como `@Controller`, que indicam classes que desempenham esse papel.

#### **Consequências**
**Ao implementar o padrão Controlador, o sistema se beneficia das seguintes características:**
1. **Centralização de Controle**: A responsabilidade pelo controle de fluxo é centralizada em um ou mais controladores, tornando o comportamento do sistema mais previsível e organizado.

2. **Alta Coesão**: Ao manter a lógica de controle separada das outras camadas, as responsabilidades ficam melhor distribuídas, evitando a sobrecarga de módulos com funcionalidades desconectadas.

3. **Facilidade de Manutenção**: Como a lógica de controle está concentrada nos controladores, modificações no comportamento de resposta a eventos podem ser feitas diretamente nesses módulos, sem impactar outras partes do sistema.

4. **Baixo Acoplamento**: O controlador interage com outros módulos de forma orquestrada, delegando responsabilidades às classes que realmente as possuem, o que facilita alterações e evolução do sistema.

Por outro lado, se não for bem implementado, o padrão controlador pode gerar um módulo com responsabilidades excessivas, conhecido como **God Class** ou "Classe Deus", que concentra demasiadas funcionalidades, dificultando a manutenção e aumentando a complexidade do sistema.

### *Exemplo Prático*
Imagine um sistema de loja on-line onde, ao finalizar um pedido, o cliente aciona um evento para fechar o pedido. A classe `ControladorFechamentoPedido` poderia ser responsável por:

1. Receber a solicitação de fechamento de pedido.
2. Verificar se os itens no pedido estão disponíveis no estoque.
3. Calcular o valor total do pedido.
4. Registrar a operação no sistema.
5. Notificar o cliente sobre a confirmação do pedido.

Neste caso, o controlador **não executa diretamente** as verificações e cálculos, mas sim delega essas responsabilidades para classes especializadas, como `Estoque`, `Pedido` e `Notificador`. Assim, a lógica do fluxo é mantida coesa e centralizada no controlador, enquanto as responsabilidades operacionais estão distribuídas.

### **Considerações Finais**

O padrão GRASP **Controlador** é uma das abordagens mais eficazes para organizar a lógica de controle e coordenar o fluxo de eventos dentro de um sistema, garantindo uma estrutura mais organizada e facilitando a manutenção e evolução. Contudo, ==deve-se tomar cuidado para que o controlador não assuma responsabilidades demais, o que geraria um módulo excessivamente complexo e de difícil gestão.==

## Polimorfismo

### *Definição*
O padrão **Polimorfismo** no contexto do GRASP (General Responsibility Assignment Software Patterns) é utilizado para organizar a responsabilidade de implementar variações de um comportamento específico de maneira flexível e extensível. ==No paradigma orientado a objetos, o polimorfismo permite que métodos em classes diferentes compartilhem a mesma assinatura, mas possuam implementações distintas.== Isso possibilita que uma mesma operação seja executada de várias maneiras, dependendo da classe que a implementa.

Por exemplo, considere um sistema de pagamento que suporta diferentes brokers (intermediários de pagamento). Com o polimorfismo, o sistema pode tratar de maneira uniforme diferentes brokers, sem precisar se preocupar com qual broker específico está sendo utilizado em tempo de execução.

#### **Problema**
Em muitos sistemas de software, precisamos lidar com variações de comportamento que dependem do tipo de elemento envolvido. Por exemplo, imagine um software de loja virtual que se conecta a diferentes brokers de pagamento, cada um com uma API específica e comportamentos diferentes.

Para resolver esse problema sem utilizar polimorfismo, podemos implementar uma série de condicionais (`if-else` ou `switch-case`) que verifiquem qual broker está sendo utilizado e chamem a implementação correta. No entanto, esse método gera alto acoplamento entre o módulo que chama e as diferentes implementações. Assim, a manutenção e a inclusão de novos brokers se tornam complexas, já que exigem alterações no código principal sempre que um novo broker é adicionado.

**Essa abordagem pode resultar em:**
1. **Código extenso e de difícil leitura**: Com múltiplas verificações de condição.
2. **Alto acoplamento**: A classe controladora depende diretamente de cada implementação de broker.
3. **Baixa escalabilidade**: Para cada novo broker, é necessário alterar a lógica de verificação, comprometendo a estrutura do sistema.

*O problema é, então, como evitar a proliferação de estruturas condicionais e criar um sistema mais flexível para tratar variações de comportamento?*

#### **Solução**
A solução é utilizar **polimorfismo**. O padrão sugere a criação de uma **interface genérica** que define o comportamento esperado (por exemplo, `ProcessarPagamento`). Em seguida, são criadas diferentes classes que implementam essa interface, cada uma correspondendo a um broker específico. Dessa forma, o módulo chamador pode interagir com qualquer broker de maneira transparente, sem se preocupar com a implementação específica de cada um.

Assim, a estrutura condicional é substituída por uma **única chamada** à interface genérica. O sistema invoca o método que deseja executar e, em tempo de execução, o método correto (implementado pela classe concreta específica) é acionado.

**Passos para implementar a solução:**
1. **Definir uma interface genérica**: Que representa a funcionalidade esperada (ex: `interface BrokerPagamento`).
2. **Criar classes específicas**: Que implementam a interface para cada broker (ex: `BrokerA`, `BrokerB`, `BrokerC`).
3. **Utilizar a interface como referência**: O sistema trabalha com a interface (`BrokerPagamento`), e em tempo de execução, a instância concreta é atribuída dinamicamente.

**Exemplo:**
```java
// Definição da interface genérica
public interface BrokerPagamento {
    void processarPagamento(double valor);
}

// Implementação específica para o Broker A
public class BrokerA implements BrokerPagamento {
    @Override
    public void processarPagamento(double valor) {
        System.out.println("Processando pagamento via Broker A: " + valor);
    }
}

// Implementação específica para o Broker B
public class BrokerB implements BrokerPagamento {
    @Override
    public void processarPagamento(double valor) {
        System.out.println("Processando pagamento via Broker B: " + valor);
    }
}

// Classe que utiliza polimorfismo
public class ProcessadorPagamento {
    private BrokerPagamento broker;

    public ProcessadorPagamento(BrokerPagamento broker) {
        this.broker = broker;
    }

    public void executarPagamento(double valor) {
        broker.processarPagamento(valor); // Chamada polimórfica
    }
}
```

No exemplo acima, `ProcessadorPagamento` utiliza a interface `BrokerPagamento` e, em tempo de execução, a implementação correta (por exemplo, `BrokerA` ou `BrokerB`) é atribuída ao atributo `broker`. A classe `ProcessadorPagamento` não precisa saber detalhes das diferentes implementações de brokers, tornando o código mais modular e fácil de manter.

#### **Consequências**
**O uso do padrão Polimorfismo traz várias vantagens:**
1. **Baixo Acoplamento**: O chamador não precisa conhecer as implementações específicas, apenas a interface que define o comportamento esperado.
2. **Alta Extensibilidade**: Novas implementações podem ser adicionadas sem modificar o código existente. Para adicionar um novo broker, basta criar uma nova classe que implemente a interface `BrokerPagamento`.
3. **Manutenção Simplificada**: Modificações em uma implementação específica não impactam o chamador, desde que a interface genérica seja mantida.

==Porém, é necessário ter cuidado ao utilizar polimorfismo em cenários onde não há variações suficientes para justificar a flexibilidade adicional.== Implementar estruturas polimórficas em casos onde não há variação resulta em um design excessivamente complexo, desnecessário e mais difícil de gerenciar.

### *Aplicação do Polimorfismo em Padrões de Projeto*
**O princípio de polimorfismo é amplamente utilizado em diversos padrões de design, como:**
- **Adapter**: Para converter a interface de uma classe em outra que o cliente espera.
- **Command**: Para encapsular uma solicitação como um objeto, permitindo parametrizar clientes com diferentes solicitações.
- **Composite**: Para compor objetos em estruturas de árvore e tratar objetos individuais e composições de forma uniforme.
- **Proxy**: Para fornecer um substituto ou marcador para outro objeto para controlar o acesso a ele.
- **State**: Para permitir que um objeto altere seu comportamento quando seu estado interno muda.
- **Strategy**: Para definir uma família de algoritmos, encapsulá-los e torná-los intercambiáveis.

Cada um desses padrões se beneficia do polimorfismo ao permitir que diferentes implementações sejam tratadas de maneira uniforme, promovendo um design orientado a interfaces e reduzindo o acoplamento entre módulos.

### *Considerações Finais*
O padrão GRASP **Polimorfismo** oferece uma solução robusta para evitar estruturas condicionais complexas e, ao mesmo tempo, manter o código flexível e adaptável. É uma ferramenta poderosa, especialmente em cenários onde variações de comportamento são esperadas. Contudo, ==deve ser usado com cautela para não complicar o design em situações que não exigem tal flexibilidade.==