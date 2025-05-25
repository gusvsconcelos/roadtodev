## ✅ RESUMO PARA PROVAS – PROCESSOS E GERÊNCIA DE PROCESSADOR

---

### 🔹 CONCEITOS FUNDAMENTAIS

- **Processo**: programa em execução; possui contador de instruções, registradores, variáveis, e é uma entidade ativa.
- **Espaço de endereçamento**: área de memória acessada pelo processo.
- **PID**: identificador único de um processo.
    

#### Estados de um processo:

1. **Novo**
2. **Pronto**
3. **Executando**
4. **Bloqueado**
5. **Terminado**

#### Mudança de contexto:

- Troca de um processo por outro na CPU.
- Salva e restaura contextos de hardware, software e memória.

---

### 🔹 CRIAÇÃO E FINALIZAÇÃO DE PROCESSOS

**Eventos que criam processos:**

- Inicialização do sistema
- Chamada de sistema (ex: `fork()`)
- Ação do usuário
- Tarefa em lote

**Finalização de processos:**

- Saída normal
- Erro fatal
- Erro voluntário
- Interrompido por outro processo (`kill()`)

**Hierarquia:**

- Processos criam filhos, formando uma árvore (ex: `systemd` no Linux).

---

### 🔹 PROCESSOS NO LINUX

- **`fork()`**: cria processo filho idêntico ao pai.
- **`waitpid()`**: aguarda fim de execução do filho.
- **`execve()`**: substitui imagem do processo.
- **`exit()`**: finaliza execução.

#### BCP (Bloco de Controle de Processo):

- Mantido pelo SO para cada processo.
- Contém: estado, prioridade, registradores, gerenciamento de memória, E/S, etc.

---

### 🔹 THREADS (PROCESSOS LEVES)

- Executam concorrentemente dentro de um mesmo processo.
- Compartilham:
    - Espaço de endereçamento
    - Arquivos abertos
    - Variáveis globais
- Cada thread possui:
    - Conjunto próprio de registradores
    - Sua própria pilha

**Vantagens:**
- Menor custo que subprocessos
- Melhor desempenho em multiprocessadores

**Criação no Linux:**
- **`clone()`** com `CLONE_VM`, `CLONE_FILES`, `CLONE_FS`, etc.

---
### 🔹 TIPOS DE PROCESSOS

- **CPU-bound**: uso intenso da CPU (ex: simulações científicas)
- **I/O-bound**: muitos acessos a dispositivos de E/S (ex: bancos de dados)

---

### 🔹 COMUNICAÇÃO E SINCRONIZAÇÃO ENTRE PROCESSOS

#### 1. **Condição de corrida**

- Ocupação simultânea de região crítica por vários processos
- Resultados inesperados e inconsistências

#### 2. **Região Crítica**

- Trecho do código que acessa recurso compartilhado

#### 3. **Exclusão mútua**

- Garante que apenas um processo acesse a região crítica por vez

#### 4. **Semáforos**

- `down(mutex)`: tenta entrar na região crítica
- `up(mutex)`: libera a região crítica
    
- Garantem acesso sincronizado

#### 5. **Monitores**

- Estruturas de alto nível que encapsulam variáveis e procedimentos
- Usam exclusão implícita (ex: `synchronized` em Java)

---

### 🔹 COMUNICAÇÃO ENTRE PROCESSOS NO LINUX

- **Pipe (`|`)**: conecta saída de um processo à entrada de outro
- **Sinais**: notificam processos sobre eventos (ex: `SIGINT`, `SIGKILL`)
- **Chamada `kill()`**: envia sinal a outro processo

---

### 🔹 ESCALONAMENTO DE PROCESSOS

- Decide qual processo será executado
- Pode ser:
    - **Preemptivo**: interrupção permitida
    - **Não preemptivo**: processo não pode ser interrompido

#### Algoritmos:

| Algoritmo           | Tipo           | Característica principal                                   |
| ------------------- | -------------- | ---------------------------------------------------------- |
| **FIFO (FCFS)**     | Não preemptivo | Primeiro a chegar, primeiro a ser servido                  |
| **SJF**             | Não preemptivo | Menor tempo de execução primeiro                           |
| **SRTN**            | Preemptivo     | Variante do SJF com tempo restante mais curto              |
| **Cooperativo**     | Não preemptivo | Libera CPU voluntariamente                                 |
| **Round Robin**     | Preemptivo     | Quantum (time slice) fixo por processo                     |
| **Prioridade**      | Preemptivo     | Processos com prioridade mais alta são executados primeiro |
| **Múltiplas filas** | Variado        | Várias filas com diferentes algor. por tipo de processo    |

---

## 🖊️ QUESTÕES COMENTADAS – PROCESSOS E GERENCIAMENTO

**1.** Em relação à chamada de sistema `fork()` no Linux, é correto afirmar:

A) Cria processo com o mesmo PID do pai.
B) Cria cópia do processo pai, com espaço de endereçamento compartilhado.
C) Cria um novo processo com espaço de endereçamento independente.
D) Executa diretamente outro programa.  
E) Não permite criação de mais de um processo filho.

✅ **Gabarito: C**

> **Comentário**: A `fork()` cria um processo filho idêntico ao pai, com espaço de memória independente.

---

**2.** Sobre estados de processos, assinale a correta:

A) Terminado significa que o processo já foi removido da memória.  
B) Bloqueado indica que o processo está utilizando a CPU.  
C) Processo passa de bloqueado para pronto após completar E/S.  
D) Novo é o estado em que o processo já está executando.  
E) Pronto indica que o processo está sendo finalizado.

✅ **Gabarito: C**

> **Comentário**: Após concluir uma E/S, o processo vai para pronto, aguardando CPU.

---

**3.** Em relação à condição de corrida:

A) Ocorre quando threads estão em diferentes processos.  
B) É resolvida com execução paralela.  
C) Decorre do acesso simultâneo e descontrolado a dados compartilhados.  
D) Não ocorre com uso de semáforos.  
E) Pode ser ignorada em sistemas monoprogramáveis.

✅ **Gabarito: C**

> **Comentário**: A condição de corrida surge quando dois ou mais processos acessam simultaneamente uma região crítica sem controle.

---

**4.** Qual algoritmo de escalonamento garante fatia de tempo igual para todos os processos?

A) FIFO  
B) SJF  
C) Round Robin  
D) Prioridade  
E) Cooperativo

✅ **Gabarito: C**

> **Comentário**: Round Robin distribui a CPU em time slices iguais para todos.

---

**5.** Sobre threads no Linux, assinale a correta:

A) Sempre possuem o mesmo PID do processo pai.  
B) São criadas por `fork()`.  
C) Compartilham espaço de endereçamento com o processo.  
D) Cada thread possui sua própria tabela de processos.  
E) São gerenciadas apenas pelo kernel.

✅ **Gabarito: C**

> **Comentário**: Threads compartilham memória com o processo e entre si, tornando-os mais leves.