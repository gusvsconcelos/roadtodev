# **Conceitos do Azure: Modelos e Nuvem**

## Modelos de Nuvem

### *Nuvem Pública*
- **Definição**: Criada e mantida por um provedor de terceiros, a nuvem pública é um ambiente de fácil acesso, onde qualquer pessoa com uma conexão à internet pode utilizar os recursos oferecidos.
- **Provedores**: Microsoft Azure, Amazon Web Services (AWS), e Google Cloud são alguns dos principais provedores.
- **Casos de Uso**: Organizações com necessidades variáveis e que buscam uma infraestrutura econômica e de rápida implementação.
#### ***Vantagens***
- **Economia de Custos**: Nenhum gasto inicial com infraestrutura, pagando-se apenas pelo uso.
- **Escalabilidade**: Provisionamento rápido e fácil dos recursos, possibilitando escalar conforme necessário.
- **Manutenção**: O provedor é responsável pela segurança física, manutenção e atualização do hardware.
  
### *Nuvem Privada*
- **Definição**: Ambiente exclusivo para uma única organização, operado internamente ou por um terceiro, garantindo maior controle e personalização.
- **Desvantagens**: Maior custo e necessidade de manutenção contínua.
- **Casos de Uso**: Organizações que trabalham com dados sensíveis e que precisam de um alto nível de controle, como bancos e agências governamentais.
#### ***Características***
- **Controle Total**: Organização gerencia a segurança, recursos e personalizações do ambiente.
- **Maior Segurança**: Não compartilha recursos com outras empresas, garantindo mais privacidade e segurança.

### *Nuvem Híbrida*
- **Definição**: Integra tanto a nuvem pública quanto a privada, permitindo que dados e aplicações transitem entre os dois ambientes.
- **Casos de Uso**: Empresas que buscam uma solução flexível para expandir sua capacidade de infraestrutura sem comprometer a segurança de seus dados.
#### ***Características***
- **Flexibilidade**: Oferece o melhor dos dois mundos, possibilitando armazenamento e processamento de dados sensíveis em uma nuvem privada, enquanto usa a nuvem pública para dados menos críticos.
- **Escalabilidade sob Demanda**: Empresas podem usar recursos adicionais da nuvem pública temporariamente para atender a picos de demanda.

### *Multicloud*
- **Definição**: Utilização de múltiplos provedores de nuvem simultaneamente, como Microsoft Azure, AWS e Google Cloud.
- **Casos de Uso**: Organizações que desejam diversificar seus serviços e ter maior segurança contra falhas de provedores.
#### ***Benefícios***
  - **Resiliência**: Evita dependência de um único fornecedor.
   - **Flexibilidade e Otimização de Custo**: Organizações podem escolher serviços com melhor custo-benefício de diferentes provedores para atender a diversas necessidades.
   
## Tipos de Serviço de Nuvem

Os serviços de nuvem do Azure são classificados em três modelos principais, cada um atendendo a diferentes níveis de controle, flexibilidade e responsabilidade.

### *IaaS (Infraestrutura como Serviço)*
- **Descrição**: Provedor oferece infraestrutura básica, como servidores, armazenamento e redes, enquanto o cliente gerencia o sistema operacional, middleware e aplicativos.
- **Exemplos no Azure**: Máquinas Virtuais (VMs), Redes Virtuais.
- **Casos de Uso**: Hospedagem de aplicativos que requerem controle total sobre o SO ou de sistemas legados que não foram desenvolvidos para plataformas modernas.
#### ***Responsabilidade***
- **Provedor**: Manutenção do hardware, segurança física, rede e virtualização.
- **Cliente**: Sistema operacional, aplicativos, dados e segurança de rede.

### *PaaS (Plataforma como Serviço)*
- **Descrição**: Oferece uma plataforma que inclui infraestrutura e ferramentas de desenvolvimento, para que o cliente possa desenvolver, gerenciar e hospedar aplicações sem se preocupar com o gerenciamento da infraestrutura.
- **Exemplos no Azure**: Azure App Services, Azure SQL Database.
- **Casos de Uso**: Desenvolvimento rápido de aplicativos, sem a necessidade de gerenciar infraestrutura, ideal para projetos que necessitam de integração contínua e suporte a múltiplos ambientes.
#### ***Responsabilidade***
- **Provedor**: Gerenciamento de infraestrutura, segurança física e lógica, sistema operacional e ferramentas de desenvolvimento.
- **Cliente**: Desenvolvimento, implantação e gerenciamento dos dados e do código da aplicação.

### *SaaS (Software como Serviço)*
- **Descrição**: Oferece aplicativos prontos, gerenciados pelo provedor de nuvem, e acessíveis via internet.
- **Exemplos no Azure**: Office 365, Dynamics CRM.
- **Casos de Uso**: Empresas que preferem soluções completas e geridas para atender a necessidades específicas, como software de email, CRM ou ERP.
#### ***Responsabilidade***
- **Provedor**: Toda a infraestrutura, dados, aplicativo e manutenção.
- **Cliente**: Gerenciamento e segurança dos dados inseridos no sistema, controle dos acessos dos usuários e dispositivos.

## Modelo de Responsabilidade Compartilhada

O modelo de responsabilidade compartilhada divide as obrigações entre o cliente e o provedor de nuvem, com base no tipo de serviço contratado (**IaaS**, **PaaS**, **SaaS**).

### *Exemplo IaaS*
>O provedor gerencia a infraestrutura física e virtual, enquanto o cliente cuida de todos os aspectos do sistema operacional, incluindo patches de segurança, configuração e gerenciamento de dados.

- **Caso Prático**: Uma empresa cria uma máquina virtual no Azure para hospedar um servidor de banco de dados. A Microsoft cuida da infraestrutura subjacente, mas a empresa é responsável pela configuração e manutenção do banco de dados.

### *Exemplo PaaS*
>O provedor oferece e mantém a infraestrutura, enquanto o cliente se preocupa apenas com os dados e o código da aplicação.

- **Caso Prático**: A empresa desenvolve uma aplicação no Azure App Services. A Microsoft gerencia o SO e a infraestrutura, permitindo que a empresa foque em desenvolver o aplicativo.

### *Exemplo SaaS*
>O provedor é responsável por tudo, com exceção dos dados e acessos, que são geridos pelo cliente.

- **Caso Prático**: Utilizando o Office 365, a Microsoft cuida de toda a infraestrutura e do software, enquanto a empresa gerencia o controle de acessos e os dados dos usuários.

## Modelo de Consumo: CapEx e OpEx

### *CapEx (Despesas de Capital)*
>Investimentos em infraestrutura física, como servidores e redes, que exigem um gasto inicial e custos de manutenção.

- **Exemplo**: Construção de um datacenter.

### *OpEx (Despesas Operacionais)*
>Pagamento contínuo pelo uso de recursos, sem a necessidade de comprar e gerenciar infraestrutura.

- **Exemplo**: Pagamento por uso do Azure conforme necessidade, sem gastos iniciais altos.

### ***Benefícios do Modelo Baseado em Consumo***
- **Sem Custos Iniciais**: Pague conforme a utilização.
- **Escalabilidade sob Demanda**: Recursos adicionais podem ser alocados quando necessário.
- **Eficiência de Custos**: Somente os recursos utilizados são pagos, evitando gastos desnecessários.