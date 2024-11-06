# **Aplicações Práticas do Azure**
## Migração para o Azure

### *Plataforma de Migração do Azure*
- **Definição**: Conjunto de ferramentas integradas para facilitar a migração de servidores, bancos de dados e aplicativos da infraestrutura local para o Azure.
#### ***Funcionalidades***
- **Descoberta e Avaliação**: Ferramentas para identificar e avaliar a infraestrutura existente, planejando a migração conforme as necessidades específicas.
- **Migração e Modernização**: Recursos para transferir dados e modernizar aplicativos durante ou após a migração.

### *Etapas de Migração*
#### ***Descoberta e Avaliação***
- **Objetivo**: Levantar e analisar a infraestrutura e os aplicativos locais, dimensionando corretamente os recursos no Azure.
- **Ferramentas Disponíveis**: Azure Migrate e ferramentas de terceiros para descobrir as dependências dos sistemas e calcular a capacidade necessária.
   
#### ***Migração***
- **Processo**: Envolve a movimentação de dados, aplicativos e infraestrutura para o ambiente Azure.
#### ***Serviços de Suporte***
- **Azure Migrate**: Ferramenta centralizada para avaliação e migração de servidores físicos e virtuais.
- **Database Migration Service (DMS)**: Migra bancos de dados para o Azure SQL Database, SQL Managed Instance, e outros bancos de dados no Azure.
#### ***Modernização***
- **Objetivo**: Atualizar a arquitetura e as tecnologias usadas nos aplicativos migrados para aproveitar ao máximo os serviços em nuvem.
- **Exemplo Prático**: Converter um banco de dados hospedado em máquina virtual para o Azure SQL Database, que é um serviço totalmente gerenciado.

### *Exemplos de Cenários de Migração*
- **Servidores e Bancos de Dados**: Avaliar e migrar servidores físicos e bancos de dados locais para VMs ou serviços de banco de dados gerenciados no Azure.
- **Aplicativos Web**: Migração de aplicativos web para o Azure App Service, o que permite escalar automaticamente conforme a demanda.
- **Área de Trabalho Virtual**: Migrar VDI (infraestrutura de área de trabalho virtual) para o Azure Virtual Desktop, oferecendo aos usuários um ambiente de trabalho virtual seguro e acessível de qualquer lugar.
- **Armazenamento de Dados**: Migrar grandes volumes de dados com o Azure Data Box, uma solução econômica para transferir dados físicos.

## Serviço de Aplicativo do Azure

### *Azure App Service*
- **Definição**: Plataforma PaaS para criar, hospedar e gerenciar aplicativos web, APIs e back-ends de dispositivos móveis, com suporte a diversas linguagens e frameworks.
#### ***Vantagens***
- **Hospedagem Gerenciada**: Elimina a necessidade de gerenciar servidores, já que o Azure cuida da infraestrutura.
- **Escalabilidade Automática**: Recursos podem ser aumentados ou reduzidos automaticamente conforme a carga.
- **Alta Disponibilidade**: Distribuição geográfica e redundância garantem que os aplicativos permaneçam ativos.
   
### *Funcionalidades do Azure App Service*
- **Suporte a Linguagens e Frameworks**: Permite desenvolver em linguagens como .NET, Java, Ruby, Node.js, PHP e Python.
#### ***Integração com CI/CD (Continuous Integration and Continuous Deployment)***
- **Descrição**: Facilita o desenvolvimento contínuo ao integrar-se com ferramentas como GitHub, Azure DevOps e GitLab.
- **Benefício**: Permite que atualizações de código sejam testadas e implantadas automaticamente, sem tempo de inatividade.
#### ***Ambientes e Segurança***
- **Redes Virtuais e Serviço de Aplicativo Isolado**: Os aplicativos podem ser executados em redes virtuais privadas e ambientes isolados, garantindo maior segurança e conformidade.
- **Compliance**: Possui certificações rigorosas, como SOC e PCI, adequadas para empresas que precisam de altos padrões de segurança.

### *Tipos de Aplicativos no Azure App Service*
- **Aplicativos Web**: Hospedagem de sites e sistemas acessíveis via navegador.
- **APIs**: Hospedagem de APIs RESTful para comunicação entre diferentes sistemas e dispositivos.
- **Aplicativos de Back-end para Dispositivos Móveis**: Facilita a criação de back-ends para aplicativos móveis, permitindo a integração com notificações e autenticação.
- **WebJobs**: Permite a execução de tarefas de segundo plano associadas a um aplicativo web, como processar dados ou enviar e-mails.

### *Planos de Serviço*
- **Definição**: O Azure App Service é executado dentro de um plano de serviço, que determina a quantidade de recursos disponíveis para o aplicativo.
#### ***Tipos de Planos e Capacidades***
Os planos variam de acordo com o nível de recurso, como CPU e RAM, e suportam diferentes quantidades de aplicativos. Por exemplo:
- **B1, S1, P1v2, I1v1**: Suporta até 8 aplicativos.
- **B2, S2, P2v2, I2v1**: Suporta até 16 aplicativos.
- **Exemplo Prático**: Se um aplicativo precisar de alta capacidade de processamento e armazenamento, o usuário pode escolher um plano de serviço premium com suporte a escalabilidade automática e recursos de segurança avançada.

## Kubernetes e Containers no Azure

### *Azure Kubernetes Service (AKS)*
- **Definição**: Serviço gerenciado de orquestração de contêineres, baseado em Kubernetes, que facilita o gerenciamento de aplicativos em contêineres.
#### ***Vantagens:***
- **Orquestração Automatizada**: Garante a distribuição e balanceamento de carga dos contêineres, além de permitir escalabilidade automática.
- **Integração com Azure DevOps**: Permite implantações contínuas e automáticas, facilitando o desenvolvimento de software ágil.
   
### *Azure Container Instances (ACI)*
- **Definição**: Serviço que permite executar contêineres rapidamente, sem a necessidade de gerenciar infraestrutura de VM ou Kubernetes.
#### ***Benefícios***
- **Agilidade e Simplicidade**: Ideal para tarefas rápidas e pontuais, como testes de código ou processamento de dados temporário.
- **Exemplo Prático**: Executar um contêiner de processamento de imagem para redimensionamento em lote e, em seguida, desligar automaticamente.

### *Vantagens de Containers no Azure*
- **Flexibilidade e Escalabilidade**: Os contêineres podem ser escalados automaticamente, facilitando o gerenciamento de cargas variáveis.
- **Economia de Recursos**: Com contêineres, é possível usar menos recursos de infraestrutura, pois eles são leves e mais fáceis de inicializar e parar do que VMs tradicionais.

## Ferramentas de Modernização e Otimização

### *Azure DevOps*
- **Definição**: Conjunto de ferramentas que permite a automação de processos de desenvolvimento, teste e implantação de aplicativos.
#### ***Funcionalidades***
- **Pipelines de CI/CD**: Facilitam a entrega contínua de código, com testes automatizados e implantação rápida.
- **Boards e Repositórios**: Integram funcionalidades para gerenciamento de projetos, controle de versão e repositórios de código.

### *Insights de Migração*
- **Definição**: Ferramenta de análise que utiliza dados de uso para otimizar o dimensionamento dos recursos após a migração.
- **Exemplo Prático**: Ajustar a configuração de VMs para reduzir custos com base nas estatísticas de uso coletadas após a migração.

### *Azure Cost Management*
- **Descrição**: Ferramenta para monitorar e gerenciar custos de forma contínua, facilitando a criação de alertas e relatórios.
- **Benefício**: Ajuda a manter os gastos sob controle, promovendo uma melhor alocação dos recursos financeiros e aumentando a eficiência.