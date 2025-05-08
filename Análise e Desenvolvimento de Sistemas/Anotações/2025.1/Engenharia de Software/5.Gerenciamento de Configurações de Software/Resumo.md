## ✅ RESUMO PARA PROVAS – GERENCIAMENTO DE CONFIGURAÇÃO DE SOFTWARE (GCS)

---
### 📌 1. O QUE É GCS?

- **Gerenciamento de Configuração de Software (GCS)** ==é o conjunto de atividades que controla e registra as alterações no software==, garantindo qualidade, rastreabilidade e consistência durante todo o ciclo de vida do projeto.

---
### 🧱 2. ELEMENTOS DO GCS (segundo Pressman)

1. **Componentes**: ferramentas que controlam arquivos e itens de configuração.
2. **Processo**: define como as mudanças são gerenciadas.
3. **Construção**: automatiza o processo de build (compilação/ligação).
4. **Fator humano**: equipe treinada e com papéis bem definidos.

---
### 📄 3. PLANO DE GCS

Documento que descreve:
    
- Itens de configuração (ICS)
- Ferramentas usadas
- Procedimentos de auditoria e controle
- Responsáveis por cada entrega

---
### 🧩 4. ICS (Item de Configuração de Software)

- Qualquer artefato criado no processo (documentos, código, testes, ferramentas, etc.)
- **Referência**: ICS formalmente revisado e aprovado, usado como base para evolução futura.

---
### 🔁 5. TAREFAS DO GCS (Pressman)

1. **Identificação**: definir e catalogar ICS.
2. **Controle de versão**: manter histórico e rastreabilidade.
3. **Controle de alteração**: processar e aprovar mudanças.
4. **Auditoria de configuração**: verificar consistência e integridade.
5. **Relato de status**: gerar informações sobre o estado atual da configuração.

---
### 🔄 6. GERENCIAMENTO DE MUDANÇAS

#### Etapas:

1. **Recebimento do FSM** (Formulário de Solicitação de Mudança)
2. **Avaliação de impacto e custo**
3. **Aprovação pelo Comitê de Controle de Mudança (CCM)**
4. **Execução, verificação e validação**
5. **Atualização do repositório**

#### Exemplos de ferramentas:

- Jira, Bugzilla, ClearQuest

---
### 📚 7. GERENCIAMENTO DE VERSÕES

- Controla diferentes versões dos componentes.
- Garante que múltiplos desenvolvedores trabalhem sem conflito.

#### Conceitos:

- **Codeline**: sequência de versões de um componente.
- **Baseline**: versão estável com conjunto fixo de ICS.

#### Tipos:

- **Centralizado** (SVN)
- **Distribuído** (Git)

#### Operações:

- **Check-out**: copiar item para trabalhar.
- **Check-in**: devolver item ao repositório.
- **Commit**: agrupar e salvar alterações.
- **Push/Pull**: enviar/obter dados no Git.

---
### 🚀 8. GERENCIAMENTO DE RELEASES

- **Release** = versão entregue ao cliente. Pode incluir código, documentação, dados e configurações.
- **Major release**: grandes funcionalidades.
- **Minor release**: correções/melhorias.

---
### 🛠️ 9. CONSTRUÇÃO DE SISTEMAS (BUILD)

- Processo de transformar código-fonte em executável.
- Envolve:
    - Compilação
    - Ligação de bibliotecas
    - Configuração de ambiente

#### Fases:

1. **Sistema de desenvolvimento** (compilação local)
2. **Servidor de construção** (build centralizado)
3. **Ambiente de destino** (execução final)

#### Ferramentas:

- Jenkins, Ant, Maven, Make, Gradle

---
### 🔄 10. INTEGRAÇÃO CONTÍNUA

- Construção e testes frequentes.
- Etapas:
    1. Desenvolvedor faz alterações localmente.
    2. Executa testes.
    3. Envia para repositório.
    4. Sistema recompila e testa.
    5. Se passar, vira baseline.
- Vantagens: detecção precoce de falhas, integração segura e constante.

---
### ⚙️ 11. FERRAMENTAS CASE

- **CASE (Computer-Aided Software Engineering)**: ferramentas para automação de tarefas de engenharia de software.

#### Tipos:

- **Suporte individual**: controle de versão, mudança, integração.
- **Suporte ao projeto**: colaboração entre membros.
- **Suporte à organização**: integração com processos de negócio.

#### Exemplos:

| Tipo             | Open Source         | Comerciais               |
| ---------------- | ------------------- | ------------------------ |
| Versão           | Git, SVN, CVS       | ClearCase, StarTeam      |
| Mudança          | Bugzilla, Trac      | Jira, ClearQuest         |
| Build/Integração | Jenkins, Maven, Ant | BuildForge, FinalBuilder |

---
### 🧠 PALAVRAS-CHAVE QUE COSTUMAM CAIR

- GCS, ICS, baseline, codeline, check-in, check-out, commit, push, pull, build, repositório, integração contínua, delta, referência, ferramenta CASE, Rational ClearCase, auditoria, rastreabilidade, mudança, release.

---
## 📝 **Questões de Fixação – GCS**

**1. (FCC – 2019 – Técnico em Informática – Manaus)**  
No repositório SVN, qual operação cria uma cópia de trabalho para edição?

A) Check-out  
B) Diff  
C) Perform  
D) Commit  
E) Update

✅ **Gabarito: A**

> _Comentário_: Check-out copia os arquivos do repositório para edição local.

**2. (FGV – 2019 – DPE-RJ – Analista TI)**  
O software foi corrigido, mas erros antigos voltaram a ocorrer. Qual disciplina falhou?

A) Gestão de Configuração de Software  
B) Especificação de Requisitos  
C) Gestão de Riscos  
D) Medição  
E) Comunicação com o Cliente

✅ **Gabarito: A**

> _Comentário_: O GCS evita regressões e garante integridade entre versões.

**3. (FCC – 2008 – Companhia de Processamento de Dados da Bahia)**  
Assinale a alternativa que **não** corresponde a uma ferramenta de GCS:

A) CVS  
B) Subversion  
C) ClearCase  
D) Ms-Project  
E) JEDI

✅ **Gabarito: D**

> _Comentário_: MS Project é voltado a gestão de projetos, não a controle de versões.

**4. (FCC – 2018 – SEFAZ-SC – Auditor Fiscal)**  
A configuração de software se trata de:

A) Item de hardware gerenciado isoladamente  
B) Instância identificada de um item de software  
C) Versão acordada de um item de software  
D) Versão formalmente aprovada de um item  
E) Característica funcional e física de hardware/software conforme documentado

✅ **Gabarito: E**

> _Comentário_: Essa é a definição formal de configuração de software.

**5. (FCC – 2019 – Web Designer – Manaus)**  
Salvar no repositório mudanças feitas em uma cópia de trabalho corresponde à operação:

A) Commit  
B) Check-out  
C) Status  
D) Revisão  
E) Update

✅ **Gabarito: A**

> _Comentário_: Commit registra e envia alterações ao repositório.