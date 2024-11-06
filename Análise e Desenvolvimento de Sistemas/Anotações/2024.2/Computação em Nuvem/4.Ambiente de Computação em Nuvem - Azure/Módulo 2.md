# **A Arquitetura e os Serviços do Azure**

## Infraestrutura Física e Regiões do Azure

### *Datacenters*
- **Definição**: São as instalações físicas que formam a base do Azure, compostas por servidores, sistemas de refrigeração, sistemas de backup de energia, entre outros.
- **Distribuição Global**: Os datacenters são estrategicamente localizados ao redor do mundo, permitindo que empresas escolham onde seus dados serão armazenados para garantir baixa latência e conformidade regulatória.
- **Redundância e Segurança**: Cada datacenter é equipado com tecnologia de segurança avançada e backup, mantendo a disponibilidade e a proteção dos dados.

### *Regiões do Azure*
- **Definição**: São áreas geográficas que contêm um ou mais datacenters interconectados e próximos.
- **Funcionalidade**: As regiões permitem às empresas escolherem onde hospedar seus recursos, garantindo que os dados permaneçam em um local específico para atender a regulamentações de soberania de dados.
- **Benefícios**: Escolher uma região próxima aumenta a performance e minimiza latência para usuários locais.

### *Zonas de Disponibilidade (Availability Zones)*
- **Definição**: São datacenters separados fisicamente, mas interligados dentro da mesma região, garantindo alta disponibilidade e resiliência contra falhas locais.
- **Casos de Uso**: Aplicações críticas que precisam de alta disponibilidade podem ser distribuídas entre várias zonas para evitar downtime.
#### ***Características***
- Cada zona possui infraestrutura própria e independente, como energia e rede.
- Garante que, se uma zona falhar, as outras continuarão funcionando.

### *Pares de Regiões (Region Pairs)*
- **Definição**: Cada região do Azure possui uma região par, geralmente dentro do mesmo país ou a até 300 milhas (aproximadamente 480 km) de distância.
#### ***Benefícios***
Em caso de falha regional, o Azure realiza failover automático para o par, minimizando o impacto em desastres naturais, apagões ou outros eventos graves.

**Exemplo**: Se um serviço na região Leste dos EUA falhar, ele pode ser transferido automaticamente para a região Oeste dos EUA.

## Contas e Assinaturas do Azure

### *Assinatura (Subscription)*
- **Definição**: Estrutura lógica que agrupa e organiza recursos dentro do Azure.
#### ***Funções***
- Controle de custos: Cada assinatura tem um orçamento que ajuda no controle financeiro dos recursos.
- Autorização de Acesso: Definem o acesso e as permissões dos usuários e recursos.

**Exemplo Prático**: Uma empresa pode criar assinaturas separadas para cada departamento (TI, Marketing, Financeiro), facilitando o controle de custos e a governança.

### *Contas Gratuitas do Azure*
> Oferecem recursos gratuitos por um período (geralmente 12 meses), incluindo um crédito inicial e acesso a serviços populares sem custo.

### *Recursos e Grupos de Recursos*
- **Recursos**: São componentes utilizáveis no Azure, como máquinas virtuais, redes e bancos de dados.
- **Grupos de Recursos**: Servem para organizar recursos relacionados, facilitando o gerenciamento e a aplicação de políticas.
- **Exemplo Prático**: Uma equipe de desenvolvimento pode criar um grupo de recursos contendo VMs, redes e bancos de dados necessários para um projeto, permitindo que políticas e orçamentos sejam aplicados ao grupo.

## Serviços de Computação do Azure

### *Máquinas Virtuais (VMs)*
- **Definição**: Servidores virtualizados que permitem ao usuário criar e gerenciar ambientes com controle total sobre o sistema operacional.
- **Casos de Uso**: Executar aplicativos que exigem personalização do SO, rodar softwares personalizados e configurar ambientes específicos.
- **Conjuntos de Escala de Máquinas Virtuais (VM Scale Sets)**: Automação para criar e gerenciar grupos de VMs idênticas, permitindo escalabilidade com balanceamento de carga.

### *Azure Virtual Desktop (Área de Trabalho Virtual)*
- **Definição**: Ambiente de área de trabalho hospedado na nuvem, acessível de qualquer lugar e em qualquer dispositivo.
- **Vantagens**: Suporte para múltiplas sessões em Windows 10/11 Enterprise, facilitando a colaboração e reduzindo os custos de licenciamento.

### *Contêineres*
- **Definição**: Soluções leves que permitem empacotar e executar aplicativos isoladamente, sem necessidade de gerenciar o SO.
- **Comparação com VMs**: Contêineres são mais ágeis e leves, sendo ideais para implementações rápidas e escaláveis.
- **Exemplos**: Docker no Azure, e Instâncias de Contêiner do Azure (ACI), que oferecem uma plataforma PaaS para execução de contêineres.

### *Azure Functions*
- **Definição**: Computação serverless orientada a eventos, onde uma função é ativada e executada apenas quando um evento específico ocorre.
- **Vantagens**: Redução de custos, pois os recursos só são consumidos durante a execução do código, eliminando a necessidade de infraestrutura constante.
- **Exemplo Prático**: Envio automático de uma notificação por e-mail quando um novo arquivo é adicionado ao Azure Blob Storage.

### *Serviço de Aplicativo do Azure (Azure App Service)*
- **Definição**: Plataforma PaaS para hospedar e gerenciar aplicativos web, APIs e back-ends de dispositivos móveis.
#### ***Recursos***
- Suporte a várias linguagens de programação (C#, Java, Python, Node.js).
- Escalabilidade automática, alta disponibilidade e integração com ferramentas de CI/CD, como GitHub e Azure DevOps.

## Rede no Azure

### *Rede Virtual (VNet)*
- **Definição**: Rede de nuvem que conecta recursos do Azure, podendo se comunicar com redes locais e com a internet.
#### ***Funcionalidades***
- **Segmentação e Isolamento**: Organiza recursos em sub-redes para aumentar a segurança.
#### ***Pontos de Extremidade*** 
- **Públicos**: Acessíveis pela internet.
- **Privados**: Restritos a uma rede virtual específica.

### *VPNs (Redes Virtuais Privadas)*
- **Função**: Conecta redes locais a redes do Azure de forma segura, usando criptografia.
#### ***Tipos de Conexão***
- **Site a Site**: Conecta redes inteiras.
- **Ponto a Site**: Conecta dispositivos individuais.
- **Rede a Rede**: Conecta duas redes virtuais.

### *Azure ExpressRoute*
- **Definição**: Conexão privada entre redes locais e o Azure, proporcionando maior segurança e baixa latência em comparação com a internet pública.
- **Benefícios**: Melhor desempenho e segurança para transferir grandes quantidades de dados ou para aplicações com alto nível de compliance e confidencialidade.

### *DNS do Azure*
- **Definição**: Serviço de hospedagem de domínios DNS, permitindo que recursos no Azure sejam acessados por nomes de domínio personalizados.
- **Vantagens**: Utilização da infraestrutura do Azure, confiável e de fácil integração, para gerenciar registros DNS.

## Serviços de Armazenamento do Azure

### *Tipos de Armazenamento*
**Blobs (Blob Storage)**: Armazenamento de dados não estruturados, como vídeos, imagens e documentos, acessíveis de qualquer lugar.
- **Camadas de Acesso**:
- **Hot (Quente)**: Para dados acessados frequentemente.
- **Cool (Frio)**: Dados acessados ocasionalmente, armazenados por longos períodos.
- **Archive (Arquivo)**: Para dados raramente acessados, com custo reduzido.
   
**Arquivos (Azure Files)**: Armazenamento compatível com protocolos SMB e NFS, permitindo compartilhamento de arquivos na nuvem.
- **Benefícios**: Alta disponibilidade e integração com redes locais.
   
**Filas (Queues)**: Armazenamento de mensagens para processamento assíncrono, como logs e mensagens entre componentes de aplicação.

**Discos (Disks)**: Armazenamento para discos de máquinas virtuais, utilizado em nível de bloco.

### *Opções de Redundância*
- **LRS (Armazenamento com Redundância Local)**: Replicação dos dados no mesmo datacenter.
- **ZRS (Armazenamento com Redundância de Zona)**: Replicação em três zonas diferentes dentro da mesma região.
- **GRS (Armazenamento com Redundância Geográfica)**: Replicação dos dados em uma região secundária distante.
- **GZRS (Armazenamento com Redundância de Zona Geográfica)**: Combina redundância geográfica com redundância de zona, para alta durabilidade e resiliência.