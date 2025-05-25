# **Funções de Manipulação de Arquivos**

## 1. Operações básicas

> *📁 Manipulação de arquivos é essencial para armazenar, processar e registrar dados.*

**Operações principais**:

- `open()` abre arquivos
- `close()` fecha arquivos
- `read()` lê conteúdo
- `write()` insere conteúdo

**Tipos de caminho**:

- **Absoluto**: Caminho completo (ex: `/user/docs/arquivo.txt`)
- **Relativo**: Com base no diretório atual

> *📌 Use `os.path.abspath()` e `os.path.relpath()` para manipular caminhos dinamicamente.*

**Modos de acesso**:

- `r`: leitura
- `w`: escrita (sobrescreve)
- `a`: append (adiciona no final)
- `b`: binário
- `t`: texto (padrão)
- `r+`: leitura e escrita

---
## 2. Atributos e leitura/escrita

> *🧠 Atributos ajudam a controlar estado e evitar erros em tempo de execução.*

**Atributos úteis**:

- `.name`: nome do arquivo
- `.mode`: modo de abertura
- `.closed`: status do arquivo

**Leitura**:

- `read()`: lê tudo
- `readline()`: lê linha atual
- `readlines()`: retorna lista de linhas

**Escrita**:

- `write()`: escreve string
- `writelines()`: escreve lista de strings

> *⚠️ Adicione `\n` manualmente em `writelines()` se quiser quebras de linha.*

**Boas práticas**:

- Use `with open(...) as ...:` para fechar arquivos automaticamente

```python
with open('arquivo.txt', 'r') as f:
    conteudo = f.read()
```

---
## 3. Manipulando arquivo-texto

> *🛠️ Arquivos de texto são úteis em automações, relatórios e logs simples.*

**Exemplo de uso**:

- Captura dados do usuário via `input()`
- Armazena em `meu_arquivo.txt`
- Converte conteúdo para maiúsculo com `.upper()`
- Sobrescreve o arquivo com o novo conteúdo

> *💡 Use listas para coletar entradas antes de salvar: mais limpo, mais rápido.*

---
## 4. Trabalhando com dados binários

> *💾 Modo binário é ideal para imagens, vídeos e integrações de baixo nível.*

**Modos binários**:

- `rb`: leitura binária
- `wb`: escrita binária

**Aplicações comuns**:

- Manipular arquivos de mídia
- Troca de dados com sistemas legados
- Compactação e criptografia