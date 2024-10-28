# **Tecnologias Habilitadoras da Computação em Nuvem**

## Virtualização

A virtualização permite dividir um servidor físico em múltiplos ambientes independentes, otimizando o uso de hardware. Utiliza um **hypervisor** que gerencia os recursos de hardware, podendo ser:
- **Tipo 1 (bare-metal):** ==Executa diretamente no hardware==, comum em servidores.
- **Tipo 2 (hosted):** ==Executa como software sobre o sistema operacional==, comum em desktops (ex.: VirtualBox).

### *Tipos de virtualização*
- **Completa:** O hypervisor emula o hardware físico para as máquinas virtuais, possibilitando a execução de qualquer sistema.
- **Paravirtualização:** Hardware similar ao real, permitindo modificações e otimizando a performance.

## Conteinerização

A **conteinerização** (ex.: *Docker*) permite executar múltiplas aplicações isoladas em contêineres sobre o mesmo sistema operacional, consumindo menos recursos que uma máquina virtual. É ideal para ambientes leves, já que compartilha o kernel do sistema, e oferece portabilidade entre ambientes físicos e virtuais.

## Serverless Computing

A **computação sem servidor** (serverless) hospeda funções de forma escalonável e ==paga apenas pelo tempo de execução.== Funciona sem servidores dedicados, reduzindo custos e complexidade. Principais provedores incluem AWS, Google Cloud e Azure.

## ASP (Application Service Provider)

Provedores ASP oferecem aplicações pela internet, eliminando a necessidade de infraestrutura própria. Exemplo: Google Docs e webmails, acessíveis via login sem necessidade de instalação.

## Grid Computing e Utility Computing

**Grid Computing** combina múltiplos servidores para dividir o processamento de grandes cargas, sendo usada para resolver problemas que requerem muita computação. Já o **Utility Computing** foca no pagamento sob demanda para recursos básicos como processamento e armazenamento, dando flexibilidade e escalabilidade.