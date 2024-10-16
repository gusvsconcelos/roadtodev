# **Principais padrões GoF**

## Padrão Factory Method

**Definição do Padrão Factory Method:**
==O padrão **Factory Method** define uma interface para a criação de um objeto, mas permite que subclasses decidam qual classe instanciar.== Esse padrão é utilizado quando um sistema precisa trabalhar com diferentes tipos de objetos que compartilham uma interface comum, mas cuja implementação concreta pode variar.

### *Contexto de Uso*
Imagine que você está desenvolvendo um sistema para recuperar dados de arquivos em diferentes formatos (JSON, XML, PDF, etc.). Em vez de ter um código centralizado que instancia diretamente as classes específicas (como `LeitorJSON`, `LeitorXML`, `LeitorPDF`), ==o padrão Factory Method permite a criação de um objeto leitor de forma flexível e extensível.==

### *Problema*
Em aplicações que crescem em complexidade, o uso do operador `new` para criar instâncias de classes específicas pode levar a um código altamente acoplado. Isso dificulta futuras modificações e amplia o risco de introduzir erros, especialmente quando é necessário alterar a lógica de criação de objetos em várias partes do sistema.

**Solução:**
==O padrão Factory Method oferece uma estrutura organizada para a criação de objetos, promovendo a extensibilidade e a flexibilidade.== **Aqui estão os componentes principais:**
1. **Produto**: Define a interface comum para os objetos criados pelo padrão.
2. **Produto Concreto**: Representa as classes que implementam a interface do Produto, como `LeitorJSON`, `LeitorXML` e `LeitorPDF`.
3. **Criador**: Declara o método de fábrica, que é responsável pela criação do objeto Produto.
4. **Criador Concreto**: Implementa o método de fábrica e retorna instâncias de classes específicas de Produto.

### *Exemplo de Aplicação do Padrão*
```java
// Produto
public interface Leitor {
    void ler(String caminho);
}

// Produtos Concretos
public class LeitorJSON implements Leitor {
    @Override
    public void ler(String caminho) {
        // Lógica para ler JSON
    }
}

public class LeitorXML implements Leitor {
    @Override
    public void ler(String caminho) {
        // Lógica para ler XML
    }
}

public class LeitorPDF implements Leitor {
    @Override
    public void ler(String caminho) {
        // Lógica para ler PDF
    }
}

// Criador
public abstract class CriadorLeitor {
    public abstract Leitor criarLeitor();
}

// Criadores Concretos
public class CriadorLeitorJSON extends CriadorLeitor {
    @Override
    public Leitor criarLeitor() {
        return new LeitorJSON();
    }
}

public class CriadorLeitorXML extends CriadorLeitor {
    @Override
    public Leitor criarLeitor() {
        return new LeitorXML();
    }
}

public class CriadorLeitorPDF extends CriadorLeitor {
    @Override
    public Leitor criarLeitor() {
        return new LeitorPDF();
    }
}

// Uso
public class Aplicacao {
    public static void main(String[] args) {
        CriadorLeitor criador = new CriadorLeitorJSON();
        Leitor leitor = criador.criarLeitor();
        leitor.ler("caminho/para/arquivo.json");
    }
}
```

### *Consequências do Padrão Factory Method*
- **Flexibilidade e Extensibilidade**: O código que usa o padrão Factory Method pode facilmente ser estendido para suportar novas classes de Produto sem modificar a lógica existente.
- **Desacoplamento**: A lógica de criação é separada do uso dos objetos, reduzindo o acoplamento entre as classes e permitindo que as implementações de Produto sejam alteradas ou substituídas sem afetar o código que utiliza essas classes.
- **Reuso de Código**: O framework que implementa o padrão pode ser utilizado em várias aplicações, promovendo a reutilização de código e evitando a duplicação.

==Esse padrão é fundamental em muitos frameworks e bibliotecas, como o Spring, onde a flexibilidade na instância de objetos é crucial para a configuração e a extensibilidade do sistema.==

## Padrão Adapter

**Definição do Padrão Adapter:**
==O padrão **Adapter** é uma solução estrutural que permite a colaboração entre classes com interfaces incompatíveis, transformando a interface de um objeto em uma interface esperada pelo cliente.== Ele pode utilizar herança e interfaces ou instâncias do objeto adaptado.

### *Contexto de Uso*
==Um exemplo prático do uso do padrão Adapter é quando um sistema precisa interagir com uma biblioteca que trabalha com uma unidade de medida diferente.== Por exemplo, um sistema que opera com ângulos em graus pode precisar utilizar uma biblioteca que trabalha com radianos. O Adapter converterá a entrada de graus para radianos antes de chamar os métodos da biblioteca.

### *Problema*
O padrão Adapter resolve a questão da compatibilidade entre sistemas que possuem interfaces diferentes. Um exemplo cotidiano seria um turista que utiliza um carregador de celular em um país onde as tomadas são diferentes. O adaptador permite que o carregador funcione na tomada local sem precisar alterar a instalação elétrica.

### *Exemplo de Aplicação do Padrão*
Suponha que estamos desenvolvendo um software de vendas para diferentes lojas de departamentos, onde cada loja pode usar uma solução de pagamento diferente. Cada fornecedor tem uma API específica para processar pagamentos, o que pode dificultar a integração.

**Solução:**
O padrão Adapter oferece uma estrutura em que um adaptador converte chamadas genéricas para chamadas específicas da API do fornecedor. **A seguir, estão os componentes principais:**
1. **Fornecedor**: Define a API proprietária (ex: `BrokerPagamentoABC`, `BrokerPagamentoXPTO`).
2. **Alvo**: Representa a interface genérica que os clientes utilizarão (ex: `BrokerPagamento`).
3. **Adaptador**: Converte chamadas da interface alvo para a API do fornecedor específico.

### *Estrutura do Padrão Adapter*
```
+------------------+        +--------------------+
|    Cliente       |        |    Alvo            |
|                  | ------>| BrokerPagamento    |
+------------------+        +--------------------+
       |                           ^
       |                           |
       v                           |
+--------------------+             |
|   Adaptador        |             |
|   AdaptadorBrokerABC|            |
|                    |<------------+
+--------------------+
```

**Exemplo de Código:**
```java
// Interface alvo
public interface BrokerPagamento {
    void pagtoEmCartaoCredito(double valor);
}

// Implementação do fornecedor
public class BrokerPagamentoABC {
    public void pagarCartaoCredito(double valor) {
        // Lógica de pagamento via cartão de crédito
    }
}

public class BrokerPagamentoXPTO {
    public void efetuarPagtoCredito(double valor) {
        // Lógica de pagamento via cartão de crédito
    }
}

// Adaptador para o BrokerPagamentoABC
public class AdaptadorBrokerABC implements BrokerPagamento {
    private BrokerPagamentoABC brokerABC;

    public AdaptadorBrokerABC(BrokerPagamentoABC brokerABC) {
        this.brokerABC = brokerABC;
    }

    @Override
    public void pagtoEmCartaoCredito(double valor) {
        brokerABC.pagarCartaoCredito(valor);
    }
}

// Adaptador para o BrokerPagamentoXPTO
public class AdaptadorBrokerXPTO implements BrokerPagamento {
    private BrokerPagamentoXPTO brokerXPTO;

    public AdaptadorBrokerXPTO(BrokerPagamentoXPTO brokerXPTO) {
        this.brokerXPTO = brokerXPTO;
    }

    @Override
    public void pagtoEmCartaoCredito(double valor) {
        brokerXPTO.efetuarPagtoCredito(valor);
    }
}

// Uso do adaptador
public class SistemaVendas {
    private BrokerPagamento brokerPagamento;

    public SistemaVendas(BrokerPagamento brokerPagamento) {
        this.brokerPagamento = brokerPagamento;
    }

    public void realizarPagamento(double valor) {
        brokerPagamento.pagtoEmCartaoCredito(valor);
    }
}

// Exemplo de uso
public class Main {
    public static void main(String[] args) {
        BrokerPagamentoABC brokerABC = new BrokerPagamentoABC();
        BrokerPagamento adaptadorABC = new AdaptadorBrokerABC(brokerABC);

        SistemaVendas sistema = new SistemaVendas(adaptadorABC);
        sistema.realizarPagamento(100.0);
    }
}
```

### *Consequências do Padrão Adapter*
- **Incorporação de Módulos Existentes**: Permite a inclusão de módulos previamente desenvolvidos sem necessidade de alterar suas interfaces originais.
- **Interface Unificada**: Proporciona uma interface comum para diferentes implementações, facilitando a integração e a reutilização de código.
- **Desacoplamento**: Os módulos clientes não precisam conhecer a implementação específica dos fornecedores, reduzindo a dependência e aumentando a flexibilidade do sistema.

==O padrão Adapter é, portanto, uma solução poderosa para integrar sistemas que necessitam trabalhar com APIs ou componentes diferentes, mantendo a coesão e a flexibilidade do software.==

## Padrão Facade

**Definição do Padrão Facade:**
==O padrão **Facade** é um padrão estrutural que fornece uma interface simplificada para um conjunto de interfaces em um subsistema, reduzindo a complexidade e aumentando a legibilidade do código.== Ele serve como uma "fachada" que concentra as chamadas a diversos componentes ou subsistemas, facilitando a interação com sistemas complexos.

### *Problema*
Em sistemas onde múltiplas chamadas complexas precisam ser feitas, especialmente em interfaces gráficas, o código pode se tornar extenso e difícil de manter. O padrão Facade oferece uma solução para esse problema ao fornecer uma interface única, evitando que o código da interface gráfica precise lidar com a complexidade das interações subjacentes.

**Exemplo do Problema:**
Considere uma classe `GUIPontoDeVenda` que precisa realizar várias operações para registrar itens vendidos:
  1. Buscar um produto usando `ProdutoRepository`.
  2. Criar um `ItemVenda`.
  3. Adicionar o item a uma venda.
  4. Salvar as informações da venda usando `VendaRepository`.

==Essa implementação pode gerar muitas dependências e tornar a manutenção do código difícil.==

**Solução:**
A introdução de uma classe **`ServicoVenda`** como fachada simplifica o processo. Em vez de várias chamadas a diferentes classes, o sistema agora faz uma única chamada ao método `registrarItem` da fachada, que por sua vez encapsula toda a lógica necessária.

### *Estrutura do Padrão Facade*
```
+------------------+
|    GUI           |
|  Ponto de Venda  |
+------------------+
        |
        | (chama)
        v
+------------------+
|   ServicoVenda   |  <-- Fachada
+------------------+
        |
        | (chama)
        v
+------------------+
| ProdutoRepository|
+------------------+
+------------------+
|  VendaRepository |
+------------------+
```

### *Consequências do Padrão Facade*
- **Redução da Complexidade**: O padrão facilita o uso, tornando o sistema mais intuitivo e reduzindo a necessidade de interagir diretamente com múltiplas interfaces.
- **Desacoplamento**: A camada de interface com o usuário é isolada da lógica de negócio, promovendo um menor acoplamento entre as diferentes partes do sistema.
- **Abstração**: O padrão encapsula os detalhes de implementação, permitindo que o cliente interaja com uma interface simplificada, sem se preocupar com a complexidade subjacente.

### *Considerações Finais*
==O padrão Facade é especialmente útil em sistemas grandes e complexos, onde a clareza e a manutenção do código são essenciais.== Ele melhora a experiência do desenvolvedor e do usuário ao fornecer uma interface mais amigável e de fácil compreensão para operações que, de outra forma, seriam complicadas.

## Padrão Strategy

**Definição do Padrão Strategy:**
==O padrão **Strategy** é um padrão comportamental que permite definir uma família de algoritmos, encapsular cada um deles e torná-los intercambiáveis.== Ele oferece uma maneira organizada de lidar com várias ações distintas que devem ser executadas dependendo de uma condição específica, evitando a complexidade gerada por estruturas condicionais como `if` e `else`.

### *Problema*
O padrão Strategy soluciona o problema de gerenciar diferentes algoritmos que podem ser aplicados a uma tarefa específica. Por exemplo, em uma loja de departamentos, pode haver várias políticas de desconto aplicáveis em diferentes épocas do ano (Natal, Páscoa, etc.). A questão é como organizar esses algoritmos de modo que novas políticas possam ser adicionadas sem modificar o código existente, respeitando o princípio **Open/Closed**.

**Solução:**
O padrão Strategy define uma interface comum para todos os algoritmos (estratégias), e cada implementação específica do algoritmo é encapsulada em sua própria classe. O **contexto** (a classe que utiliza as estratégias) pode invocar qualquer estratégia, que é injetada no contexto. Isso permite que novos algoritmos sejam adicionados à família sem impactar o código já implementado.

### *Estrutura do Padrão Strategy*
```
+-------------------+
|      Contexto     |
|                   |
|   +-----------+   |
|   | Estrategia|<--| 
|   +-----------+   |
|         |         |
|         v         |
|   +-----------+   |
|   | EstrategiaA|  |
|   +-----------+   |
|   | EstrategiaB|  |
|   +-----------+   |
|   | EstrategiaC|  |
|   +-----------+   |
+-------------------+
```

### *Exemplo do Padrão Strategy*
No exemplo da loja de departamentos, a classe **Venda** pode ter uma política de desconto associada no momento de sua instância. Para calcular o valor a ser pago pelo cliente, basta chamar o método `aplicar` da instância de **PoliticaDesconto** associada à venda.

**Diagrama de Exemplo:**
```
+--------------+
|    Venda     |
|              |
|   +-------+  |
|   | PoliticaDesconto|<--| 
|   +-------+  |
|              |
+--------------+
```

Para obter o valor total a ser pago, a classe **Venda** calcula o valor total dos itens e subtrai o valor retornado pela política de desconto aplicada.

### *Consequências*
- **O padrão Strategy separa os algoritmos dos elementos que precisam executá-los**, permitindo a aplicação de diferentes tipos de algoritmos (como política de desconto, cálculo de frete, etc.) sem a necessidade de modificações no código que os utiliza.
- **Ele proporciona uma solução elegante e extensível para o encapsulamento de algoritmos**, permitindo que as implementações sejam isoladas das classes que as utilizam. Isso também elimina a necessidade de estruturas condicionais complexas, que são comuns quando variações não são implementadas usando esse padrão.

### *Considerações Finais*
==O padrão Strategy é altamente versátil e útil em situações onde diferentes comportamentos ou algoritmos precisam ser aplicados de forma intercambiável.== Ele melhora a manutenibilidade e extensibilidade do código, tornando-o mais organizado e menos propenso a erros.

## Padrão Template Method

**Definição do Padrão Template Method:**
==O padrão **Template Method** é um padrão comportamental que permite definir a estrutura de um algoritmo em uma classe base, deixando alguns passos do algoritmo para serem implementados por subclasses.== Isso possibilita a reutilização de código e a personalização de partes específicas do algoritmo, sem alterar sua estrutura geral.

### *Problema*
O padrão Template Method é aplicável em situações onde diferentes implementações de um processo compartilham etapas comuns, mas requerem variações em algumas partes. Por exemplo, ao implementar máquinas de bebidas, tanto a máquina de café quanto a de chá têm passos semelhantes, **mas cada uma possui etapas específicas:**

**Máquina de Café:**
1. Esquentar a água.
2. Preparar a mistura (moagem do café).
3. Colocar a mistura no copo.
4. Adicionar açúcar, se selecionado.
5. Adicionar leite, se selecionado.
6. Liberar a bebida.

**Máquina de Chá:**
1. Esquentar a água.
2. Preparar a mistura (infusão do chá).
3. Colocar a mistura no copo.
4. Adicionar açúcar, se selecionado.
5. Adicionar limão, se selecionado.
6. Liberar a bebida.

O desafio é implementar essas variações sem duplicar código nem criar uma única implementação com muitas estruturas condicionais.

**Solução:**
O padrão Template Method propõe que a classe base defina um método genérico que encapsula o algoritmo principal, com chamadas para métodos abstratos que serão implementados pelas subclasses. Isso mantém a estrutura do algoritmo intacta enquanto permite personalizações específicas.

### *Estrutura do Padrão Template Method*
```
+------------------------+
|  Classe Abstrata       |
|  (Template)            |
|  +-----------------+   |
|  | metodoTemplate  |   |
|  | +-------------+ |   |
|  | | metodoComum | |   |
|  | +-------------+ |   |
|  | +-------------+ |   |
|  | | metodoAbstratoA|<--|
|  | +-------------+ |   |
|  | +-------------+ |   |
|  | | metodoAbstratoB|<--|
|  | +-------------+ |   |
+------------------------+
```

### *Exemplo do Padrão Template Method*
Considerando as máquinas de café e chá, a classe abstrata **MaquinaBebida** define o método `prepararReceita`, que contém todos os passos do procedimento, incluindo as operações comuns e as específicas. Os métodos que requerem implementação específica são definidos como métodos abstratos.

**Exemplo de Código:**
```java
abstract class MaquinaBebida {
    public final void prepararReceita() {
        esquentarAgua();
        prepararMistura();
        colocarNoCopo();
        adicionarComplemento();
        liberarBebida();
    }
    
    protected void esquentarAgua() {
        // Lógica para esquentar água
    }

    protected abstract void prepararMistura(); // a ser implementado pelas subclasses
    protected void colocarNoCopo() {
        // Lógica para colocar no copo
    }
    protected abstract void adicionarComplemento(); // a ser implementado pelas subclasses
    protected void liberarBebida() {
        // Lógica para liberar a bebida
    }
}

class MaquinaCafe extends MaquinaBebida {
    @Override
    protected void prepararMistura() {
        // Lógica para moer o café
    }

    @Override
    protected void adicionarComplemento() {
        // Lógica para adicionar leite ou açúcar
    }
}

class MaquinaCha extends MaquinaBebida {
    @Override
    protected void prepararMistura() {
        // Lógica para infundir o chá
    }

    @Override
    protected void adicionarComplemento() {
        // Lógica para adicionar limão ou açúcar
    }
}
```

### *Consequências*
- **O padrão Template Method ajuda a evitar a duplicação de código**, centralizando a implementação do algoritmo em uma única classe abstrata. As variações são implementadas nas subclasses, permitindo que qualquer modificação na estrutura comum do algoritmo seja feita em um único lugar.
- **Esse padrão é amplamente utilizado em frameworks**, onde a estrutura de controle é invertida, ou seja, a superclasse é responsável por chamar os métodos definidos nas subclasses, seguindo o princípio de Hollywood: "Não nos chame, nós chamaremos".

### *Considerações Finais*
==O padrão Template Method é uma ferramenta poderosa para garantir a reutilização de código e a flexibilidade em sistemas que compartilham uma estrutura comum, mas têm necessidades específicas.== Ele melhora a manutenibilidade do código e permite que novos comportamentos sejam adicionados de forma limpa e organizada.