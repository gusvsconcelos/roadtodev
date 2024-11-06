# **Gerenciamento, Governança e Monitoramento do Azure**
## Gerenciamento de Custos no Azure

### *Calculadora de Preço*
- **Descrição**: Ferramenta online que permite estimar o custo dos recursos no Azure, considerando fatores como localização, tipo de recurso e volume.
#### ***Funcionalidades***
- Possibilita a criação de cenários personalizados e armazenamento de estimativas.
- Exporta orçamentos para formatos como Excel, facilitando a integração com processos financeiros da organização.

### *Calculadora de TCO (Total Cost of Ownership)*
- **Definição**: Ferramenta focada em comparar os custos entre infraestrutura local e nuvem, considerando despesas operacionais e de capital.
- **Objetivo**: Ajuda na tomada de decisão sobre a migração para a nuvem, avaliando a economia potencial em um horizonte de até 5 anos.
- **Exemplo Prático**: Uma empresa pode usar a calculadora de TCO para estimar os custos ao transferir seus servidores físicos para máquinas virtuais no Azure.

### *Gerenciamento de Custos e Análise de Custo*
- **Gerenciamento de Custos**: Centraliza as informações de gastos e permite definir orçamentos com limites financeiros para controlar o uso dos recursos.
- **Análise de Custo**: Oferece visualizações detalhadas dos custos por ciclo de cobrança, por recurso ou por região.
- **Exemplo Prático**: Criar um orçamento de R$ 20.000,00 para monitorar gastos e configurar um alerta para enviar um e-mail quando o uso atingir 80% desse valor.

### *Tags (Marcas)*
- **Definição**: Metadados associados a recursos ou grupos de recursos, usados para categorizar e organizar melhor os ativos.
- **Benefícios**: Permite filtros e relatórios por marca, facilitando a alocação de custos por departamento ou projeto.
- **Exemplo Prático**: Marcar todos os recursos utilizados pelo setor de RH com a tag “RH”, e os recursos do setor de TI com a tag “TI”, para gerar relatórios específicos de cada setor.

## Governança e Conformidade no Azure

### *Azure Policy*
- **Descrição**: Serviço para criar e gerenciar políticas que controlam e auditam a conformidade dos recursos com padrões corporativos e de segurança.
#### ***Funcionalidades***
- Avaliação automática dos recursos para identificar inconsistências com as políticas.
- **Iniciativas**: Agrupamento de várias políticas relacionadas em um único pacote.
- **Exemplo Prático**: Impor uma política que restringe a criação de VMs apenas em regiões específicas para garantir conformidade com regulamentos de dados.

### *Bloqueios de Recursos (Resource Locks)*
- **Definição**: Mecanismo de proteção que impede a exclusão ou modificação de recursos críticos.
#### ***Tipos de Bloqueio***
- **Delete (Exclusão)**: Restringe a exclusão, mas permite a leitura e modificação.
- **ReadOnly (Somente Leitura)**: Restringe exclusão e atualização, permitindo apenas leitura.
- **Exemplo Prático**: Aplicar um bloqueio “ReadOnly” em um grupo de recursos que contenha dados sensíveis, garantindo que nenhuma alteração seja feita por erro.

### *RBAC (Controle de Acesso Baseado em Funções)*
- **Descrição**: Sistema de autorização que controla quem tem acesso aos recursos, o que pode ser feito e a quais recursos o acesso é permitido.
#### ***Funcionalidade***
- Permite segmentar permissões por função e por grupo, garantindo que apenas as equipes responsáveis tenham acesso aos recursos específicos.
- **Exemplo Prático**: Limitar o acesso a um grupo de recursos de finanças apenas aos funcionários do departamento financeiro, usando o RBAC para garantir que apenas eles possam realizar operações nesses recursos.

### *Portal de Confiança do Serviço (Service Trust Portal)*
- **Descrição**: Portal com documentos, ferramentas e recursos relacionados à segurança, privacidade e conformidade do Azure.
- **Benefícios**: Oferece acesso a certificações, auditorias e normas regulatórias, como NIST e ISO 27001, facilitando a comprovação de conformidade.
- **Exemplo Prático**: Utilizar o portal para obter documentos de conformidade quando necessário demonstrar que o Azure atende aos requisitos de segurança de um órgão regulador.

## Ferramentas de Monitoramento do Azure

### *Azure Advisor*
- **Descrição**: Assistente que analisa continuamente os recursos do Azure e fornece recomendações em cinco áreas: confiabilidade, segurança, desempenho, excelência operacional e custo.
#### ***Funcionalidade***
- Interface simples com recomendações que podem ser implementadas ou ignoradas conforme a necessidade.
- **Exemplo Prático**: Receber uma recomendação para redimensionar uma VM para uma versão menor e economizar custos, com base na análise do uso de recursos.

### *Integridade do Serviço do Azure (Service Health)*
- **Descrição**: Ferramenta para gerenciar e monitorar a integridade dos serviços do Azure, com três componentes principais:
- **Status do Azure**: Visão global dos serviços em todas as regiões, incluindo relatórios de incidentes que afetam o serviço.
- **Integridade de Serviço**: Informações detalhadas sobre a saúde dos serviços e regiões utilizadas pela organização.
- **Resource Health (Integridade de Recursos)**: Relatórios personalizados da integridade dos recursos específicos, informando se o aplicativo foi afetado.
- **Exemplo Prático**: Receber uma notificação de que uma VM enfrenta problemas de conectividade e consultar o Resource Health para obter detalhes e planejar ações.

### *Azure Monitor*
- **Descrição**: Sistema de monitoramento que coleta e analisa dados de todos os recursos do Azure, ajudando a visualizar e agir proativamente.
#### ***Funcionalidades***
- **Coleta de Dados**: Gera logs, métricas e diagnósticos sobre o desempenho de recursos e aplicativos.
- **Alertas**: Configurações de alertas automáticos com base em métricas e limites personalizados.
- **Exemplo Prático**: Criar um alerta para informar a equipe de TI quando o uso de CPU de uma VM exceder 80% por mais de cinco minutos, permitindo que a equipe ajuste a capacidade antes que o serviço seja impactado.