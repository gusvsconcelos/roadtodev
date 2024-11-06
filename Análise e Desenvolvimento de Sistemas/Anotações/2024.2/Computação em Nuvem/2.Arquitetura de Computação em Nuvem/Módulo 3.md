# **Arquitetura de Soluções em Nuvem**

## Soluções em IaaS (Infraestrutura como Serviço)

- Fornece infraestrutura para criação de aplicativos e serviços.
- Inclui componentes como servidores virtuais, ferramentas de balanceamento de carga, sistemas de gerenciamento de dados e suporte a múltiplos provedores (Multi-Cloud e Cloud Híbrida).

## Cenários de Uso do IaaS

### *Elasticidade*
==Aumenta ou reduz automaticamente os recursos conforme a demanda.==
### *Balanceamento de Carga*
Distribui o tráfego entre servidores para evitar sobrecargas e aumentar a eficiência.
### *Alta Disponibilidade*
Reduz riscos de falhas, implementando redundância e monitoramento contínuo.
### *Multi-Cloud*
Utiliza diferentes provedores de nuvem, ideal para diversificar e aumentar a disponibilidade.
### *Cloud Híbrida*
Combina nuvem pública e privada, permitindo uso local de servidores físicos e serviços externos.

## Edge Computing e Serverless

### *Edge Computing*
Processa dados localmente, o que reduz a latência e é ideal para aplicações de IoT e cenários que exigem respostas rápidas.
### *Serverless*
Permite execução de funções sem gerenciamento direto de servidores, cobrando apenas pelo uso, ideal para ambientes distribuídos e flexíveis.

## Estratégias de Migração para Nuvem (7 Rs)

1. ==**Rehost (Lift and Shift)**: Move recursos para a nuvem sem mudanças estruturais.==
2. **Replatform**: Ajusta sistemas para melhor compatibilidade com a nuvem, sem mudar a arquitetura.
3. **Repurchase**: Substitui sistemas antigos por um novo software em nuvem.
4. **Refactor**: Recria o sistema para torná-lo nativo da nuvem.
5. **Retire**: Desativa sistemas ou aplicativos desnecessários.
6. **Retain**: Mantém algumas partes localmente por razões estratégicas.
7. **Relocate**: Move infraestrutura para a nuvem mantendo os processos intactos.

## Considerações Finais

### *Vantagens da Arquitetura em Nuvem*
- **Escalabilidade**: ==Permite aumentar ou reduzir o uso de recursos conforme necessário.==
- **Elasticidade**: ==Recursos flexíveis que se ajustam automaticamente às demandas.==
- **Modelo de Pagamento Sob Demanda (Pay-as-you-go)**: ==Cobrança apenas pelos recursos efetivamente utilizados.==

### *Segurança e Redução de Custos*
- **Segurança**: Dados ficam protegidos por medidas de segurança oferecidas pelos provedores.
- **Redução de Custos**: Elimina a necessidade de investimentos pesados em infraestrutura própria e simplifica a manutenção.