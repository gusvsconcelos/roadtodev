# **Funções de manipulação de arquivos**

## 1. Operações básicas

A manipulação de arquivos em Python é essencial para executar tarefas comuns como o armazenamento de informações, processamento de dados e geração de logs.

**As operações básicas incluem**:

- **Abrir** arquivos para manipulação.
- **Fechar** arquivos após o uso.
- **Ler** informações gravadas.
- **Escrever** novos conteúdos.

### Abrindo um arquivo

==O método principal para acessar arquivos é por meio da função `open()`, que retorna um objeto representando o arquivo.== O argumento `caminho` especifica a localização do arquivo no sistema:

- **Absoluto**: Indica o endereço completo (ex.: `/home/user/documento.txt`).
- **Relativo**: Refere-se ao caminho em relação ao diretório atual.

>*Funções adicionais como `path.relpath` e `path.abspath` ajudam a manipular caminhos.*

### Modos de acesso a arquivos

**O acesso ao arquivo é configurado com diferentes modos, como**:

- **r**: Modo de leitura (padrão).
- **w**: Escreve no arquivo e apaga o conteúdo existente.
- **a**: Adiciona informações no final do arquivo.
- **b**: Manipula dados binários.
- **t**: Manipula dados no formato texto (padrão).

>*Modos combinados como `r+` permitem ler e escrever ao mesmo tempo.*

---
## 2. Atributos do objeto tipo arquivo

==Os atributos do objeto arquivo (`name`, `mode`, `closed`) são úteis para entender o estado do arquivo e gerenciar operações de forma eficiente==, reduzindo erros e melhorando a estabilidade de aplicativos.

### Fechando um arquivo

O método `close()` libera recursos alocados para o arquivo, tornando-o acessível a outros programas.

### Lendo arquivos

**Python oferece métodos para ler conteúdos**:

- `read()`: Lê todo o conteúdo como uma string.
- `readline()`: Lê uma única linha e avança para a próxima.
- `readlines()`: Retorna uma lista com cada linha do arquivo.

### Escrevendo em arquivos

**Métodos para escrita**:

- `write()`: Insere um texto no arquivo.
- `writelines()`: Grava uma coleção de strings, como uma lista.

>*É necessário inserir manualmente quebras de linha (`\n`) entre os elementos, caso necessário.*

### Boas práticas

A palavra-chave `with` é recomendada para garantir o fechamento automático dos arquivos após o uso:

```python
with open(caminho, modo) as arquivo:
    # Código dentro do contexto
```

---
## 3. Manipulando arquivo-texto em Python

==O uso de arquivos texto é comum para automação, geração de relatórios e processamento de informações.==

**Para ilustrar**:

- Capturamos dados via console, armazenando em um arquivo.
- Convertendo conteúdos para maiúsculas com `.upper()` para padronização.
- Sobrescrevemos o arquivo com os dados formatados.

**Exemplo prático**:

1. Usuário insere textos em loop (terminando ao digitar "sair").
2. Dados são salvos no arquivo `meu_arquivo.txt`.
3. O conteúdo é convertido para letras maiúsculas.
4. O arquivo original é sobrescrito.

>*Utilize listas para armazenar entradas antes de escrevê-las, otimizando a manipulação.*

---
## 4. Lidando com dados binários em arquivos

Arquivos binários permitem manipular dados como imagens e vídeos de forma compacta. ==Usando modos como **rb** e **wb**, é possível realizar operações eficientes em baixo nível, integrando sistemas legados ou aplicações multimídia.==