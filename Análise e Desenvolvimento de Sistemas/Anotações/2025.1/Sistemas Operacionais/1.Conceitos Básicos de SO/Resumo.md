## ✅ RESUMO PARA PROVAS – CONCEITOS BÁSICOS DE SISTEMAS OPERACIONAIS (SO)

---
### 🔹 1. CONCEITOS FUNDAMENTAIS

- **Sistema Operacional (SO)**: Software que atua como intermediário entre os programas de aplicação e o hardware.
    
**Funções principais**:
    
- Gerenciar hardware e software
- Coordenar execução de programas
- Abstrair e proteger o hardware

#### Componentes de um Sistema Computacional:

- **Hardware**: CPU, memória, dispositivos de E/S
- **Software**: Aplicativos e o SO
- **Usuários**: Pessoas, sistemas ou outros computadores

#### Modos de Execução:

- **Modo Usuário**: Acesso restrito, usado por programas
- **Modo Kernel (Supervisor)**: Acesso total ao hardware, reservado ao SO

#### Interface com o SO:

- **CLI (Shell)**: Interface de linha de comando
- **GUI (Interface gráfica)**: Interface com ícones e menus

---
### 🔹 2. EVOLUÇÃO DOS SISTEMAS OPERACIONAIS

#### Primeira Geração (1945-1955):

- Programados com **painéis físicos**
- Uso de **válvulas**

#### Segunda Geração (1955-1965):

- Introdução dos **transistores**
- Aparecimento dos **sistemas em lote (batch)**

#### Terceira Geração (1965-1980):

Introdução de:
    
- **Multiprogramação**
- **Time-sharing**
- **Spooling**
- **Memória virtual**
- **UNIX**

#### Quarta Geração (1980 - atual):

- **Computadores pessoais, TCP/IP, SOs multiusuários, interfaces gráficas, Internet, Open Source**

#### Unix e Windows:

- **Unix**: Reescrito em C, multiusuário, multitarefa, influenciou o Linux
- **Windows**:
    - Começou com o MS-DOS
    - Evoluiu para Windows NT, XP, 7, 10, etc.

---
### 🔹 3. TIPOS DE SISTEMAS OPERACIONAIS

| **Tipo**         | **Características**                                                      |
| ---------------- | ------------------------------------------------------------------------ |
| Monoprogramável  | Executa apenas um programa por vez. CPU ociosa durante operações de E/S. |
| Multiprogramável | Executa vários programas alternadamente. Aumenta o uso da CPU.           |
| Multiusuário     | Suporta vários usuários ao mesmo tempo.                                  |
| Multiprocessador | Usa vários processadores (SMP, NUMA, fracamente/fortemente acoplados).   |
| Tempo Real       | Executa tarefas em tempo determinístico. Crítico ou não crítico.         |
| Batch (em lote)  | Executa tarefas automaticamente sem interação do usuário.                |
| Transação        | Processa grandes volumes de pequenas requisições (ex: banco, passagens). |

#### Softwares por Licença:

- **Proprietário**: Código fechado
- **Software Livre (FSF)**: Liberdade de uso, modificação e distribuição
- **Open Source (OSI)**: Código aberto, mas não necessariamente livre

---
### 🔹 4. ESTRUTURA DO SISTEMA OPERACIONAL

#### Kernel

- Parte central do SO
- Executado em modo kernel
- Responsável por:
    - Criação/remoção de processos
    - Gerenciamento de memória
    - Escalonamento
    - Suporte a redes
    - Gerenciamento de E/S e arquivos

#### System Calls (Chamadas ao Sistema)

- Interface entre programa e kernel
- Realiza:
    - Acesso a arquivos
    - Criação de processos
    - Comunicação entre processos

#### Modos de Acesso

- **Modo kernel**: executa instruções privilegiadas
- **Modo usuário**: instruções restritas, usa system calls

#### Arquiteturas de Kernel

| **Arquitetura**      | **Características**                                                |
| -------------------- | ------------------------------------------------------------------ |
| Monolítica           | Todo o SO está em um único módulo executável                       |
| Em Camadas           | SO dividido em níveis. Mais segurança, menor desempenho            |
| Microkernel          | Apenas serviços essenciais no núcleo; outros em modo usuário       |
| VM (Virtual Machine) | Cria máquinas virtuais completas sobre o hardware real.            |
| Exokernel            | Aloca recursos diretamente; cada VM usa parte definida do hardware |

---
### 🔹 5. LINUX: INSTALAÇÃO, ESTRUTURA E COMANDOS

#### Instalação e Distribuição:

- Ex: **Ubuntu** (base Debian)
- Pode ser instalada ou executada via live CD/USB
- Versões como "20.04 LTS" indicam ano/mês e suporte

#### Diretórios do Linux:

- `/`: Raiz
- `/home`: pastas dos usuários
- `/bin`: comandos essenciais
- `/etc`: configurações
- `/var`: logs e dados variáveis
- `/tmp`: arquivos temporários
- `/dev`: dispositivos

#### Comandos básicos:

- `pwd`: mostra diretório atual
- `cd`: troca de diretório
- `ls`: lista arquivos
- `mv`: move/renomeia
- `cp`: copia arquivos
- `rm`: remove arquivos

---

## 🖊️ QUESTÕES COMENTADAS – SISTEMAS OPERACIONAIS

---

**1. (Atividade 1 - adaptada)**  
Qual das afirmações descreve corretamente a função de um sistema operacional?

A) Serve apenas para gerenciar a memória do computador.  
B) Controla e coordena o uso do hardware entre os vários programas de aplicação.  
C) Atua como um aplicativo de usuário que interconecta programas.  
D) Não tem acesso ao hardware, facilitando a segurança.  
E) É utilizado apenas para acesso à internet.

✅ **Gabarito: B**

> **Comentário**: O SO gerencia os recursos do sistema e faz a ponte entre hardware e software, coordenando seu uso pelos programas.

---

**2. (Atividade 2 - adaptada)**  
Qual evento marca a transição entre a 2ª e 3ª geração dos computadores?

A) Introdução dos computadores pessoais.  
B) Substituição das válvulas pelos transistores.  
C) Estabelecimento da multiprogramação.  
D) Desenvolvimento do primeiro microprocessador.  
E) Criação da linguagem C.

✅ **Gabarito: C**

> **Comentário**: A 3ª geração é marcada pela multiprogramação e time-sharing, avançando em eficiência.

---

**3. (Atividade 3 - adaptada)**  
Qual das alternativas descreve corretamente a evolução do Unix?

A) Foi desenvolvido pela Microsoft.  
B) Desenvolvido inicialmente em Assembly e reescrito em C.  
C) Sempre foi monoprogramável.  
D) Não influenciou outros sistemas.  
E) Foi feito para uso exclusivo em PCs.

✅ **Gabarito: B**

> **Comentário**: Unix foi criado por Ken Thompson em Assembly e depois reescrito em C, sendo base para vários SOs como Linux.

---

**4. (Atividade 1 - adaptada)**  
Qual tipo de sistema é caracterizado por desperdiço de CPU durante E/S?

A) Multiprogramação  
B) Multiusuário  
C) Monoprogramação  
D) Monousuário  
E) Hiperusuário

✅ **Gabarito: C**

> **Comentário**: Sistemas monoprogramáveis não aproveitam a CPU enquanto esperam operações de E/S.

---

**5. (Atividade 4 - adaptada)**  
Para alta segurança e confiabilidade, qual arquitetura de kernel é ideal?

A) Monolítica  
B) Em camadas  
C) Microkernel  
D) Máquina virtual  
E) Exokernel

✅ **Gabarito: C**

> **Comentário**: Microkernel executa apenas serviços essenciais no núcleo, isolando outros serviços para maior segurança.