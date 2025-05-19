## ✅ RESUMO PARA PROVAS – SISTEMAS DE ARQUIVOS (S.O.)

---

### 🔹 CONCEITOS GERAIS

- **Sistema de arquivos**: componente do S.O. que organiza, armazena e gerencia o acesso a dados.
    
- **Finalidades**:
    
    - Persistência de dados
    - Compartilhamento seguro
    - Organização e controle

#### Componentes:

- **Arquivos**: unidades lógicas de dados
- **Diretórios**: estruturas que organizam os arquivos

#### Requisitos:

- Armazenamento persistente
- Acesso concorrente
- Gerência uniforme, independente do dispositivo

---

### 🔹 ORGANIZAÇÃO E ESTRUTURA DE ARQUIVOS

#### Tipos:

- Texto (ASCII)
- Binários

#### Estrutura:

- **Sequência de bytes** (sem estrutura imposta, comum em Linux e Windows)
- **Registros de tamanho fixo**
- **Árvore de registros** (busca rápida por chave)

#### Acesso:

- **Sequencial**
- **Aleatório**
- **Indexado**

#### Tipos de arquivos:

- **Regulares**: dados genéricos
- **Diretórios**: mantém organização
- **Especiais de caractere**: dispositivos seriais
- **Especiais de bloco**: discos

---

### 🔹 ESTRUTURA DE DIRETÓRIOS

#### Modelos:

- **Nível único**: todos os arquivos em um só diretório
- **Dois níveis**: um por usuário
- **Árvore (hierárquico)**: mais usado hoje

#### Caminhos:

- **Absoluto**: inicia na raiz (/)
- **Relativo**: baseado no diretório de trabalho

#### Entradas especiais:

- `.`: diretório atual
- `..`: diretório pai

---

### 🔹 ALOCAÇÃO DE ESPAÇO EM DISCO

#### Técnicas:

- **Contígua**:
    - Arquivo em blocos sequenciais
    - ▶ Rápido, mas propenso à fragmentação
		
- **Lista encadeada**:
    
    - Blocos ligados por ponteiros
    - ▶ Permite fragmentação, acesso apenas sequencial
        
- **Lista encadeada com índice (FAT)**:
    
    - Tabela em memória indica ordem dos blocos
    - ▶ Mais rápido, mas tabela pode ser grande
        
- **Alocação indexada (i-nodes)**:
    
    - Cada arquivo tem um i-node com endereços de blocos
    - ▶ Eficiente e flexível

---

### 🔹 SISTEMA DE ARQUIVOS EXT2 / EXT3

#### EXT2:

- Estrutura:
    
    - Superbloco
    - Grupos de blocos
    - Mapas de bits (blocos/i-nodes livres)
    - i-nodes (metadados e blocos de dados)
        
- Diretórios armazenam nomes de arquivos + nº do i-node

#### EXT3 (Journaling):

- Introduz o **journaling**: transações gravadas em um diário antes de afetar o disco
- Melhora a confiabilidade e recuperação

---

### 🔹 CACHE DE DISCO

- Acesso a disco é lento → usa-se **memória cache**
- **Write-through**: grava disco imediatamente (mais seguro)
- **Write-back**: grava depois (mais rápido, maior risco)

---

### 🔹 PARTICIONAMENTO E MONTAGEM

#### Particionamento:

- Disco dividido em partes independentes
- Cada partícia pode conter um sistema de arquivos
- **MBR**: setor inicial com tabela de partíção

#### Montagem:

- Linux: partícia montada em um ponto da árvore de diretórios
    - Ex: /mnt/usb, /media/cdrom
        
- Windows: cada unidade possui uma letra (C:, D:, etc.)

---

### 🔹 COMANDOS DO LINUX

#### Manipulação de diretórios:

- `ls`: lista arquivos
- `pwd`: mostra diretório atual
- `cd`: altera diretório
- `mkdir`: cria diretório

#### Manipulação de arquivos:

- `rm`: remove arquivos
- `cp`: copia arquivos
- `mv`: move ou renomeia
- `cat`: mostra conteúdo
- `find`: busca arquivos

#### Gerenciamento:

- `fsck`: verifica e corrige sistemas de arquivos
- `df`: mostra uso de disco
- `lsblk`: lista dispositivos de bloco
- `/etc/fstab`: configura partíções a serem montadas

---

### 🔹 LINKS NO LINUX

#### Simbólicos (soft):

- Apontam para outro caminho
- Não compartilham i-node

#### Hardlinks:

- Apontam para o mesmo i-node
- Modificação afeta todos os links

---

## 🖊️ QUESTÕES COMENTADAS – SISTEMA DE ARQUIVOS

**1.** O que é o superbloco de uma partição?

A) Onde ficam os i-nodes  
B) Bloco de inicialização do sistema  
C) Parâmetros sobre o sistema de arquivos  
D) Maior bloco livre

✅ **Gabarito: C**

> **Comentário**: O superbloco contém informações críticas (tipo do sistema, blocos livres, etc.).

---

**2.** Sobre caches de disco, é correto afirmar:

A) Write-back aumenta a segurança  
B) Write-through grava disco depois  
C) Write-through grava disco imediatamente  
D) Nenhuma está correta

✅ **Gabarito: C**

> **Comentário**: O write-through é mais seguro porque grava imediatamente no disco.

---

**3.** O journaling, presente no ext3, tem como principal objetivo:

A) Melhorar desempenho de gravação  
B) Permitir nomes maiores de arquivos  
C) Garantir recuperação após falha  
D) Otimizar busca por arquivos

✅ **Gabarito: C**

> **Comentário**: O journaling protege contra perda de dados em caso de queda ou falha.

---

**4.** A alocação contígua de arquivos tem como desvantagem:

A) Acesso sequencial lento  
B) Fragmentação interna  
C) Fragmentação externa  
D) Uso elevado de ponteiros

✅ **Gabarito: C**

> **Comentário**: Exige blocos sequenciais, o que causa fragmentação externa com o tempo.

---

**5.** O comando que lista o conteúdo do diretório corrente é:

A) list  
B) ls  
C) print  
D) cat

✅ **Gabarito: B**

> **Comentário**: O `ls` é o comando padrão para listar arquivos e diretórios no Linux.