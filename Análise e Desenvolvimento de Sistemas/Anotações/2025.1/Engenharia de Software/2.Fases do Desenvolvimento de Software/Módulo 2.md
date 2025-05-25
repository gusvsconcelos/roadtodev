# **2. Projeto de Software**

## 1. Objetivo

➡️ Refinar os modelos de análise para permitir a **implementação concreta** da solução.

---
## 2. Atividades do Projeto

### Refinamento estrutural (modelo de classes)

- Adição de atributos, métodos, tipos.
- Aplicação de **padrões de projeto** (ex.: Factory Method).

### Detalhamento dinâmico (interação)

- Diagramas de sequência e comunicação.
- Mapeiam a troca de mensagens entre objetos.

> *🧩 Métodos nas classes são extraídos dessas interações.*

### Projeto da Arquitetura

➡️ Divisão do sistema em **subsistemas/coletivos lógicos**.

**Abstrações:**

| **Tipo** | **Conteúdo**                                                 |
| -------- | ------------------------------------------------------------ |
| Lógica   | Camadas: Apresentação, Aplicação, Domínio, Serviços Técnicos |
| Física   | Infraestrutura: servidores, nós, redes                       |

➡️ **Modelo em Camadas** (baixo acoplamento, alta coesão):

| **Camada**        | **Função**                   |
| ----------------- | ---------------------------- |
| Apresentação      | Interface com o usuário      |
| Aplicação         | Controle entre camadas       |
| Domínio           | Lógica de negócio            |
| Serviços técnicos | Banco de dados, persistência |

**Padrão MVC:**

- **Model**: dados e lógica.
- **View**: exibição.
- **Controller**: fluxo e ações.

### Mapeamento Objeto‑Relacional

➡️ Traduzir **objetos (UML)** em **tabelas (relacional)**.

- Diagramas de classes viram modelo conceitual do banco.
- Mapeamentos cuidam de cardinalidade (ex.: muitos‑para‑muitos).

---
## 3. Projeto da Interface

➡️ Deve garantir **usabilidade** (requisito não funcional).  

> *Participação ativa do usuário é essencial.*

**Critérios importantes:**

- Tempo de resposta
- Acessibilidade
- Ajuda integrada
- Tratamento de erros