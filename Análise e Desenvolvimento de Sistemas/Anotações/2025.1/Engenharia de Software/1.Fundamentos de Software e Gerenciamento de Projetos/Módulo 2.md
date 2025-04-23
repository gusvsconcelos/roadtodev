# **Etapas Essenciais do Processo de Desenvolvimento**

## 1. Levantamento de Requisitos

- **Funcionais**: serviços.
- **Não funcionais**: restrições/qualidade.
- **Domínio**: regras de negócio.  
  
➡️ Resultado: *Documento de Requisitos* (define escopo e inicia rastreabilidade).

---
## 2. Análise

- Converte requisitos em **modelos de alto nível** (Casos de Uso, Classes).
- Validação (usuários) + Verificação (técnica).

---
## 3. Projeto

- Refinar modelos para “**COMO**” implementar.
- Define arquitetura, componentes, BD.

---
## 4. Implementação

- Codificação alinhada aos modelos e padrões.

---
## 5. Testes

| **Fase**   | **Objetivo**            |
| ---------- | ----------------------- |
| Unitário   | Valida módulos isolados |
| Integração | Verifica interação      |
| Aceitação  | Confirma requisitos     |

> *🔄️ Automação recomendada em ciclos iterativos.*

---
## 6. Implantação

- Migração p/ produção, manuais, treinamento, suporte.

### Fluxos (Ciclos de Vida)

| **Fluxo**                               | **Uso típico**                         |
| --------------------------------------- | -------------------------------------- |
| Linear                                  | Projetos simples e estáveis            |
| Iterativo                               | Ajustes pontuais antes da próxima fase |
| Evolucionário (Iterativo + Incremental) | Versões sucessivas com valor agregado  |
| Paralelo                                | Equipes grandes, módulos independentes |
