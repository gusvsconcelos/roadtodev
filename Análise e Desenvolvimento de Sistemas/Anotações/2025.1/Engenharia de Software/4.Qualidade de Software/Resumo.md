## ✅ RESUMO PARA PROVAS – QUALIDADE DE SOFTWARE (com exercícios comentados)

---

### 📌 1. O QUE É QUALIDADE DE SOFTWARE?

- Capacidade de atender aos requisitos especificados com confiabilidade, segurança, desempenho e facilidade de manutenção.
    
- Abrange:
    
    - **Qualidade do processo**: como o software é desenvolvido.
        
    - **Qualidade do produto**: características do sistema entregue.
        

---

### 📋 2. CAMADAS DA ENGENHARIA DE SOFTWARE

1. **Qualidade**: foca em atender aos requisitos.
    
2. **Processo**: sequência de atividades (ex: análise, testes).
    
3. **Métodos**: técnicas aplicadas em cada fase.
    
4. **Ferramentas**: suporte automatizado (ex: CASE).
    

---

### 🔎 3. FATORES DE QUALIDADE (McCall)

|Fator|Avalia...|
|---|---|
|Correção|Se o software faz o que foi pedido.|
|Confiabilidade|Se funciona corretamente sem falhas.|
|Eficiência|Uso adequado de recursos.|
|Integridade|Nível de segurança contra acessos indevidos.|
|Usabilidade|Facilidade de uso pelo usuário.|
|Manutenibilidade|Facilidade de modificação/correção.|
|Flexibilidade|Facilidade para adaptar o sistema.|
|Testabilidade|Facilidade para ser testado.|
|Portabilidade|Facilidade para rodar em diferentes ambientes.|
|Reusabilidade|Pode ser reaproveitado em outros projetos.|
|Interoperabilidade|Integra-se a outros sistemas.|

---

### 🛠️ 4. GARANTIA DA QUALIDADE (SQA)

- Conjunto de ações para assegurar conformidade com os requisitos.
    
- Envolve: auditorias, padrões (ISO/IEEE), gerenciamento de mudanças e riscos.
    

---

### 🧪 5. VERIFICAÇÃO × VALIDAÇÃO

- **Verificação**: o software está sendo feito corretamente? (atividades estáticas, sem execução).
    
- **Validação**: o software certo está sendo feito? (atividades dinâmicas, com execução).
    

---

### 🔍 6. TIPOS DE TESTES

|Tipo de Teste|Objetivo|
|---|---|
|Desempenho|Avalia tempo de resposta, carga e estresse.|
|Segurança|Verifica proteção contra falhas e ataques.|
|Recuperação|Testa resposta a falhas simuladas.|
|Alpha|Realizado por usuários em ambiente controlado.|
|Beta|Feito por usuários reais, antes da entrega final.|

---

### 💸 7. CUSTOS DA QUALIDADE

- **Conformidade**:
    
    - Prevenção (ex: treinamentos)
        
    - Avaliação (ex: testes)
        
- **Não conformidade**:
    
    - Falhas internas (antes da entrega)
        
    - Falhas externas (após entrega)
        

---

### 📐 8. MÉTRICAS DE QUALIDADE

- **Medição**: coleta objetiva de dados.
    
- **Métrica**: representação quantitativa de atributos.
    
- **GQM (Goal-Question-Metric)**: modelo que liga metas, perguntas e métricas.
    

#### Principais métricas:

- **Complexidade ciclomática**: mede caminhos lógicos no código.
    
- **Fan-in / Fan-out**: indica o acoplamento entre módulos.
    
- **LOC (linhas de código)**: mede tamanho do sistema.
    

---

### 📚 9. PADRÕES ISO

|Padrão|Finalidade|
|---|---|
|**ISO 9000**|Gestão da qualidade (foco no processo).|
|**ISO 9126**|Avaliação da qualidade do produto (6 características principais).|

---

### 📘 10. QUALIDADE NO PMBOK

- **Planejar o gerenciamento da qualidade**: definir métricas e padrões.
    
- **Gerenciar a qualidade**: aplicar os processos.
    
- **Controlar a qualidade**: validar entregas conforme critérios.
    

---

### 🧠 PALAVRAS-CHAVE DE PROVA

`SQA`, `verificação`, `validação`, `teste Alpha/Beta`, `complexidade ciclomática`, `ISO 9126`, `manutenibilidade`, `eficiência`, `portabilidade`, `fan-in`, `reusabilidade`, `GQM`.

---

## 📝 QUESTÕES COMENTADAS – QUALIDADE DE SOFTWARE

---

**1. (FGV – 2019 – Analista TI)**  
O que caracteriza uma falha de software?

A) Resultado de uma alteração não documentada  
B) Erro de digitação durante o desenvolvimento  
C) Manifestação de um defeito durante a execução  
D) Parte do código que não segue o padrão  
E) Inconsistência no banco de dados

✅ **Gabarito: C**

> **Comentário**: A falha ocorre **em tempo de execução**, quando um **defeito (bug)** inserido no software é ativado.

---

**2. (CESGRANRIO – Técnico)**  
Qual o objetivo do teste de recuperação?

A) Verificar desempenho sob carga  
B) Medir tempo de resposta em diferentes plataformas  
C) Avaliar comportamento do sistema após falha simulada  
D) Garantir segurança de dados  
E) Corrigir código duplicado

✅ **Gabarito: C**

> **Comentário**: O teste de recuperação foca em verificar **como o sistema se comporta após falhas**, como quedas ou perda de dados.

---

**3. (CESPE – 2020)**  
Qual das métricas a seguir mede a complexidade do controle de fluxo de um programa?

A) Fan-in  
B) Linhas de código  
C) Complexidade ciclomática  
D) Eficiência de execução  
E) Acuracidade

✅ **Gabarito: C**

> **Comentário**: A **complexidade ciclomática** mede o **número de caminhos independentes** em um algoritmo, ajudando a definir a quantidade mínima de testes.

---

**4. (FCC – 2018)**  
Qual característica do modelo ISO 9126 está diretamente relacionada à facilidade de manutenção?

A) Portabilidade  
B) Confiabilidade  
C) Manutenibilidade  
D) Funcionalidade  
E) Eficiência

✅ **Gabarito: C**

> **Comentário**: **Manutenibilidade** trata da facilidade com que o software pode ser alterado, corrigido ou melhorado.

---

**5. (FGV – 2021)**  
Qual das opções refere-se a custo da **não conformidade**?

A) Planejamento de testes  
B) Treinamento da equipe  
C) Erro detectado pelo cliente após entrega  
D) Documentação técnica  
E) Avaliação de processos

✅ **Gabarito: C**

> **Comentário**: Falhas **externas** geram **custos de não conformidade**, pois ocorrem **após a entrega**, podendo prejudicar a imagem da empresa.