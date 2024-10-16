# **Princípios SOLID**

## Princípio da Responsabilidade Única (SRP)

O **SRP** estabelece que cada módulo ou classe deve ser responsável por apenas uma função ou ator específico. ==Isso significa que funções que atendem a diferentes usuários ou áreas do sistema não devem estar no mesmo módulo.==
  
**Exemplo:**
- Imagine um sistema de vendas que precisa de funcionalidades para busca de produtos, cadastro e exportação de dados. Essas funcionalidades atendem diferentes atores: clientes, equipe de vendas e integração de sistemas. 
- Colocar todas essas funções em uma única classe **viola o SRP**, pois a classe teria múltiplas responsabilidades e diferentes razões para mudar.
- ==A solução recomendada pelo SRP é dividir essas funcionalidades em módulos separados, cada um voltado para um único ator ou responsabilidade.==

**Benefícios do SRP**
- **Manutenção facilitada**: alterações em uma parte do sistema não afetam outras funcionalidades.
- **Escalabilidade**: módulos que exigem maior desempenho (como a busca de produtos) podem ser otimizados separadamente.

### *SOLID - Princípios de Design Orientado a Objetos*
- **S**: Single Responsibility Principle (SRP) – Responsabilidade única.
- **O**: Open-Closed Principle (OCP) – Aberto para extensão, fechado para modificação.
- **L**: Liskov Substitution Principle (LSP) – Substituição de Liskov.
- **I**: Interface Segregation Principle (ISP) – Segregação de interfaces.
- **D**: Dependency Inversion Principle (DIP) – Inversão de dependência.

## OCP - Princípio Aberto-Fechado (Open-Closed Principle)

O **OCP** estabelece que ==um módulo deve estar aberto para extensão, mas fechado para modificação==. Isso significa que é possível adicionar novos comportamentos a um sistema sem alterar o código existente, o que torna o software mais flexível e fácil de manter.

### *Violação do OCP (Clonagem)*
Um exemplo clássico de violação desse princípio ocorre quando uma classe, como `CalculadoraGeometrica`, contém métodos para calcular áreas de diferentes figuras geométricas (triângulos, quadrados, círculos). Ao adicionar uma nova figura, é necessário modificar essa classe, violando o princípio.
  
**Exemplo:**
A classe `CalculadoraGeometrica` concentra a lógica de cálculo para todas as figuras geométricas. Se novas figuras forem adicionadas (como um círculo), será necessário modificar o código, quebrando o princípio de que o módulo deve estar fechado para modificações.

**Solução - Uso de Abstração e Polimorfismo:**
A solução para essa violação é utilizar **abstração** e **polimorfismo**. Através de uma **classe abstrata** como `FiguraGeometrica`, cada figura específica implementa seu próprio método de cálculo de área. 

 **Exemplo:**
```java
public abstract class FiguraGeometrica {
	public abstract double obterArea();
}

public class Triangulo extends FiguraGeometrica {
	private double base;
	private double altura;
	
	public double obterArea() {
		return this.base * this.altura / 2;
	}
}
```
  
Assim, ao criar novos tipos de figuras geométricas, basta criar novas subclasses que implementam o método `obterArea`, sem precisar modificar a classe `CalculadoraGeometrica`.

**Vantagens do OCP:**
- Aplicando o OCP, o sistema se torna mais **modular**, permitindo a adição de novas funcionalidades sem afetar o comportamento existente.
- Evita a necessidade de alterações em módulos já validados e testados, reduzindo o risco de bugs e facilitando a **manutenção** e **evolução** do sistema.

==O OCP garante que o software seja flexível para novas necessidades e requisitos, sem a necessidade de modificar o código existente==, promovendo **escalabilidade** e **sustentabilidade** a longo prazo.

## LSP - Princípio da Substituição de Liskov (Liskov Substitution Principle)

Definido por *Barbara Liskov* em 1988, ==o princípio da substituição de Liskov estabelece que um subtipo deve ser capaz de substituir seu supertipo sem alterar o comportamento correto do sistema==. Isso significa que as subclasses devem ser capazes de ser usadas no lugar de suas classes base sem que o sistema que as utiliza seja afetado.

### *Exemplo de Violação (Quadrado e Retângulo)*
Embora um quadrado seja uma forma geométrica que pode ser vista como um retângulo, na implementação de software, a herança entre essas formas pode violar o LSP. No caso de um **retângulo**, largura e comprimento podem ter valores diferentes, mas no **quadrado** esses dois valores devem ser iguais.
  
- Se um método `verificarArea` foi projetado para trabalhar com objetos do tipo `Retangulo` e recebe um objeto do tipo `Quadrado`, ocorre uma violação do LSP, pois ao tentar definir valores diferentes para a largura e o comprimento, o quadrado quebra a expectativa do comportamento retangular.

**Problema:**
No exemplo, o quadrado herda de `Retangulo`, mas o comportamento da classe `Quadrado` é mais restrito (exige que os lados sejam iguais). Isso faz com que o princípio de Liskov seja violado, pois o comportamento esperado de um retângulo é alterado quando um quadrado é utilizado como subtipo.

**Solução:**
==Para aderir ao LSP, os subtipos não devem introduzir restrições que o supertipo não impõe==. No caso do quadrado e retângulo, uma solução mais apropriada seria tratá-los como **tipos distintos**, evitando a herança direta entre eles.

**Benefícios do LSP**
Quando o LSP é respeitado, garantimos que qualquer subtipo possa substituir seu supertipo sem que o código que o utiliza precise ser alterado ou apresente comportamento inesperado. Isso promove sistemas mais **flexíveis e robustos**, além de facilitar a **manutenção** e **extensibilidade**.

==Este princípio é fundamental para evitar erros em sistemas que utilizam herança e polimorfismo, garantindo que as subclasses possam ser utilizadas sem comprometer a lógica do sistema.==

## ISP - Princípio da Segregação de Interfaces (Interface Segregation Principle)

==O **ISP** estabelece que os clientes de uma classe não devem ser forçados a depender de operações que não utilizam==. Ou seja, as interfaces devem ser específicas e focadas em uma funcionalidade ou responsabilidade, evitando acoplamentos desnecessários.
  
- Grandes interfaces que abrangem muitas funcionalidades acabam forçando implementações a lidar com métodos que não são necessários para sua operação. Isso gera uma sobrecarga de código e baixa coesão.

### *Violação do ISP (Interfaces Grandes e Multifuncionais)*
Um exemplo clássico de violação do ISP é mostrado quando uma interface como `IUsuario` possui métodos para login, registro, registro de erros e envio de e-mail, todos dentro da mesma interface. Nem todos os usuários ou classes que implementam essa interface precisam de todas essas operações.

**Exemplo de violação:**
```java
public interface IUsuario {
	boolean login(String login, String senha);
	boolean registrar(String login, String senha, String email);
	void logErro(String msgErro);
	boolean enviarEmail(String assunto, String conteudo);
}
```

Nesse caso, classes que implementam essa interface são forçadas a lidar com métodos de envio de e-mails e registro de erros, mesmo que não precisem dessas funcionalidades.

**Segregação das Interfaces**:
Para corrigir essa violação, o ISP sugere dividir a interface grande em **interfaces menores e mais coesas**. Cada uma delas será focada em uma funcionalidade específica, garantindo que os clientes só implementem as operações que realmente precisam.

**Exemplo de segregação:**
```java
public interface IAutorizacao {
	boolean login(String login, String senha);
	boolean registrar(String login, String senha, String email);
}

public interface IEmail {
	boolean enviarEmail(String assunto, String conteudo);    
}

public interface IMensagem {
	void logErro(String msgErro);
}
```

**Agora, cada interface está relacionada a uma responsabilidade específica:**
  - `IAutorizacao`: operações de login e registro.
  - `IEmail`: envio de e-mails.
  - `IMensagem`: registro de mensagens de erro.

**Vantagens do ISP**
- **Alta Coesão**: Cada interface trata de uma única responsabilidade, tornando o código mais coeso.
- **Baixo Acoplamento**: As classes que dependem de uma interface não precisam implementar métodos que não usam, facilitando a manutenção e evolução do sistema.
- **Flexibilidade e Reusabilidade**: Com interfaces menores e específicas, é mais fácil reutilizar e manter componentes individuais.

==Aplicar o ISP torna o design de software mais modular, **focado em responsabilidades específicas**, e **evita dependências desnecessárias**, facilitando a manutenção e extensão do sistema.==

## DIP - Princípio da Inversão de Dependência (Dependency Inversion Principle)

==O **DIP** afirma que módulos de alto nível não devem depender de módulos de baixo nível==, mas ambos devem depender de abstrações. Além disso, essas abstrações não devem depender de detalhes concretos; em vez disso, os detalhes devem depender das abstrações.
  
- **Módulos de alto nível** são aqueles relacionados diretamente ao domínio do problema (por exemplo, uma classe de "Serviço de Venda").
- **Módulos de baixo nível** lidam com aspectos tecnológicos, como persistência de dados ou interface de usuário, que podem mudar com mais frequência.

### *Problema Comum: Dependência Direta de Classes Concretas*
Um exemplo de violação do DIP ocorre quando uma classe de **alto nível** (como `ServicoConsultaProduto`) depende diretamente de uma classe concreta de **baixo nível** (como `ProdutoRepositoryOracle`) para acessar um banco de dados. Isso cria um acoplamento rígido entre a lógica de negócios e a implementação tecnológica.

**Exemplo de violação:**
```java
public class ServicoConsultaProduto {
	public double obterPrecoProduto(String codigo) {
		ProdutoRepositoryOracle repo = new ProdutoRepositoryOracle();
		Produto produto = repo.obterProduto(codigo);
		return produto.getPreco();
	}
}
```

- **Por que é uma violação?** Se a tecnologia de persistência mudar (de Oracle para MySQL, por exemplo), será necessário alterar o código da classe de negócios, o que quebra a regra de "isolamento das mudanças tecnológicas" e dificulta a manutenção.

### *Solução: Abstração por meio de Interfaces*
O DIP recomenda que, em vez de depender diretamente de uma classe concreta de baixo nível, a classe de alto nível dependa de uma **interface abstrata** (ou contrato). A implementação concreta pode variar sem impactar o código que depende da interface.
  
**Exemplo de solução:**
```java
public interface ProdutoRepository {
	Produto obterProduto(String codigo);
	void salvarProduto(Produto produto);
}

public class ProdutoRepositoryOracle implements ProdutoRepository {
	public Produto obterProduto(String codigo) {
		// implementação SQL Oracle
		return new Produto();
	}
}

public class ServicoConsultaProduto {
	private ProdutoRepository repo;

	public ServicoConsultaProduto(ProdutoRepository repo) {
		this.repo = repo;
	}

	public double obterPrecoProduto(String codigo) {
		Produto produto = repo.obterProduto(codigo);
		return produto.getPreco();
	}
}
```

Agora, `ServicoConsultaProduto` depende apenas da interface `ProdutoRepository`, permitindo que outras implementações, como `ProdutoRepositoryMySQL`, sejam criadas e usadas sem alterar o código da lógica de negócio.
___
**Vantagens do DIP:**
- **Isolamento de mudanças tecnológicas**: Como o módulo de alto nível depende apenas de uma abstração, mudanças nas implementações concretas não afetam o sistema.
- **Facilidade de manutenção**: As dependências entre classes tornam-se menos rígidas, facilitando a substituição e atualização de módulos.
- **Flexibilidade e reutilização**: Novas implementações de `ProdutoRepository` podem ser adicionadas sem precisar alterar o módulo de alto nível.

==A aplicação do **DIP** é crucial para garantir que sistemas sejam **mais flexíveis, escaláveis e adaptáveis** a mudanças tecnológicas, favorecendo uma arquitetura orientada a abstrações e minimizando o impacto de mudanças em detalhes técnicos.==