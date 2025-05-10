## ✅ RESUMO PARA PROVAS – MEMÓRIA (SISTEMAS OPERACIONAIS)

---

### 🔹 CONCEITOS BÁSICOS DE MEMÓRIA

- **Memória**: Recurso essencial para execução de programas.
    
- **Hierarquia da memória**:
    
    - **Registradores / Cache** (interno, volátil, rápido e caro)
        
    - **Memória RAM** (primária, volátil)
        
    - **Armazenamento secundário** (disco, SSD, etc., não volátil)
        

#### Tipos:

- **Memória Física**: Espaço real acessado pelo hardware.
    
- **Memória Lógica (virtual)**: Espaço que o processo "enxerga".
    

#### MMU (Unidade de Gerenciamento de Memória)

- Faz o mapeamento do endereço lógico para o físico.
    
- Usa registradores base e limite para proteção de memória.
    

---

### 🔹 PROTEÇÃO E RELOCAÇÃO

- **Registrador base**: endereço inicial da memória do processo.
    
- **Registrador limite**: tamanho da memória do processo.
    

#### Relocação

- Permite que o processo seja carregado em diferentes endereços.
    
- **Estática**: feita na geração do módulo.
    
- **Dinâmica**: feita em tempo de execução pela MMU.
    

---

### 🔹 POLÍTICAS DE ALOCAÇÃO DE MEMÓRIA

#### Alocação contígua

- Processo ocupa bloco contínuo.
    
- Problema: fragmentação externa.
    

#### Overlay

- Programa é dividido em módulos que usam o mesmo espaço de memória em momentos diferentes.
    

#### Partição fixa

- Memória é dividida em partes fixas.
    
- Pode haver uma fila por partição ou uma única fila.
    
- Causa fragmentação interna.
    

#### Partição variável

- Partições dinâmicas conforme o tamanho do processo.
    
- Pode gerar fragmentação externa.
    

#### Políticas de seleção:

- **First Fit**: primeira partíção que cabe.
    
- **Best Fit**: menor partíção disponível.
    
- **Worst Fit**: maior partíção disponível.
    

#### Fragmentação

- **Interna**: espaço desperdiçado dentro da partícia.
    
- **Externa**: espaços livres não contíguos.
    

#### Compactação

- Reorganiza os blocos para formar espaço contíguo (custo alto).
    

---

### 🔹 SWAPPING (PERMUTA)

- Processo bloqueado pode ser retirado da memória e armazenado no disco.
    
- Libera espaço para outros processos.
    
- Exige **relocação dinâmica**.
    
- Desvantagem: tempo de transferência disco <-> memória é alto.
    

---

### 🔹 GERENCIAMENTO DE ESPAÇO LIVRE

- **Mapa de bits**: um bit por unidade de memória (0 = livre, 1 = ocupada)
    
- **Lista encadeada**: cada nó indica segmento livre ou ocupado
    

---

### 🔹 MEMÓRIA VIRTUAL

- Espaço de endereçamento maior que a memória física.
    
- Parte do programa fica em disco, e é carregada sob demanda.
    
- Implementada via **paginação** ou **segmentação**.
    

#### Paginação

- Divide memória em:
    
    - **Páginas** (lógicas)
        
    - **Molduras** (físicas)
        
- SO usa tabela de páginas para mapeamento.
    
- Page Fault: página requisitada não está na RAM → busca no disco.
    

#### Proteção:

- Bits de acesso (leitura, gravação, válido/inválido) por quadro.
    

#### Algoritmos de substituição:

- **FIFO**
    
- **LRU** (Least Recently Used)
    
- **NRU** (Not Recently Used)
    
- **LFU** (Least Frequently Used)
    
- **Aleatório**
    
- **Segunda chance (clock)**: baseado em bit de referência e modificado.
    

#### Working Set

- Conjunto de páginas frequentemente acessadas por um processo.
    

---

### 🔹 SEGMENTAÇÃO

- Divide programa logicamente (código, dados, stack, etc.).
    
- Endereço lógico = (segmento, deslocamento)
    
- Tabela de segmentos usada para mapeamento.
    
- Protege e organiza logicamente o espaço.
    

---

### 🔹 GERÊNCIA DE MEMÓRIA NO LINUX

#### Memória física

- Dividida em zonas:
    
    - **ZONE_DMA**: <16MB
        
    - **ZONE_DMA32**: <4GB
        
    - **ZONE_NORMAL**: memória com acesso normal
        
    - **ZONE_HIGHMEM**: memória não acessível diretamente (32 bits)
        

#### Memória virtual

- Cada processo tem:
    
    - **Visão lógica**: regiões organizadas em árvore (layout de endereçamento)
        
    - **Visão física**: mapeamento nas tabelas de páginas
        

#### Execução de programas

- `exec()`: novo layout, novo programa
    
- `fork()`: cópia do espaço de endereçamento do pai
    

#### Paginação sob demanda

- Páginas só são carregadas quando referenciadas
    
- Substituição: algoritmo do relógio (segunda chance)
    
- Kernel reserva regiões do espaço virtual para uso interno
    

---

## 🖊️ QUESTÕES COMENTADAS – GERÊNCIA DE MEMÓRIA

---

**1.** Considere um processo com registrador base = 4000 e limite = 2000. Sobre os endereços lógicos abaixo:

- 3800
    
- 5200
    
- 6200
    

Quais são acessos válidos?

A) Apenas I  
B) Apenas I e III  
C) Apenas II e III  
D) Apenas I e II  
E) II e III

✅ **Gabarito: C**

> **Comentário**: Válidos: entre 4000 (base) e 6000 (base+limite). 3800 é menor que a base → inválido. 5200 e 6200 estão no intervalo.

---

**2.** Um processo foi alocado inicialmente no endereço 4500. Após bloqueio, é relocado para 8000. Ele acessava uma variável na posição 5700. Qual novo endereço?

A) 8000  
B) 5700  
C) 9200  
D) 4500  
E) 10000

✅ **Gabarito: C**

> **Comentário**: Deslocamento = 5700 - 4500 = 1200. Novo endereço = 8000 + 1200 = 9200.

---

**3.** Qual técnica usa a menor partícia livre que comporte o processo?

A) First-Fit  
B) Worst-Fit  
C) Best-Fit  
D) Compactação  
E) Swap

✅ **Gabarito: C**

> **Comentário**: Best-Fit busca o bloco mais justo, minimizando fragmentos.

---

**4.** Em um processador com 4 bits de página e 10 de deslocamento, qual memória pode ser endereçada?

A) 8KB  
B) 16KB  
C) 24KB  
D) 32KB  
E) 64KB

✅ **Gabarito: B**

> **Comentário**: 2^4 páginas (16), cada com 2^10 bytes (1KB). 16 x 1KB = 16KB.

---

**5.** Com algoritmo LRU e 3 quadros, quantos page faults para a sequência: 1, 2, 3, 4, 2, 3, 4, 2?

A) 5  
B) 4  
C) 6  
D) 7  
E) 3

✅ **Gabarito: B**

> **Comentário**: Primeiros 3 acessos geram 3 faults. Ao acessar 4, ocorre substituição (4º fault). 2, 3 e 4 já estão em memória. Total: 4 page faults.