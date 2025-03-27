# **Funções de manipulação de arquivos**

## 1. Operações básicas

Conhecer as operações básicas de manipulação de arquivos permite a implementação eficiente de recursos, como armazenamento de dados, configurações de usuário, e processamento de entrada/saída.

- Abrir
- Fechar
- Ler
- Escrever

### Abrindo um arquivo

A primeira operação que precisamos realizar, independentemente se vamos ler o conteúdo de um arquivo ou adicionar um conteúdo, é abrir um arquivo.

Para abrir um arquivo, o Python disponibiliza a função interna chamada `open`. Essa função está disponível globalmente, ou seja, não é preciso importá-la.

A função `open` retorna um objeto do tipo arquivo. Sua forma mais simples de utilização tem a seguinte sintaxe: `arquivo = open(caminho)`

Utilizamos a função `open` com o parâmetro caminho. Esse parâmetro é uma string que representa a localização do arquivo no sistema de arquivos.

O caminho de um arquivo pode ser classificado em dois tipos:
- **Absoluto:** É a referência completa para se encontrar um arquivo ou diretório. Ele deve começar com uma barra (/) ou o rótulo do drive (C:, D:).
- **Relativo:** É a referência para se encontrar um arquivo ou diretório a partir de outro diretório. Normalmente, a partir do diretório de onde o script está.

O Python também disponibiliza algumas funções para exibir os caminhos absolutos e relativos de um arquivo ou diretório, que são:
- `path.relpath`
- `path.abspath`

### Modos de acesso a um arquivo

Quando abrimos um arquivo, precisamos informar ao Python o que desejamos fazer, ou seja, qual será o modo (mode) de acesso ao arquivo. O modo é um dos parâmetros da função `open`, e cada modo é representado por uma string.

Os principais modos são:
- `r: leitura (read)`
- `w: escrita (write)`
- `a: acrescentar (append)`

O modo padrão da função `open` é o modo leitura ("r").

Esses modos podem ser combinados e para informar que desejamos ler e escrever em um arquivo, utilizamos a string "r+", por exemplo.

O Python também nos permite diferenciar arquivos texto de arquivos binários, como uma imagem, por exemplo. Para informar que desejamos abrir uma arquivo binário, adicionamos a string "b" ao modo, ficando "rb", "wb" e "ab".

- **r**: Abre o arquivo para leitura (default).
- **w**: Abre o arquivo para escrita, truncando o arquivo primeiro.
- **x**: Cria um arquivo para escrita e falha, caso ele exista.
- **a**: Abre o arquivo para escrita, acrescentando conteúdo ao final do arquivo, caso ele exista.
- **b**: Modo binário.
- **t**: Modo texto (default).
- **+**: Abre o arquivo para atualização (leitura ou escrita).

---
## 2. Atributos do objeto tipo arquivo

Os atributos, como name, mode e closed, fornecem informações essenciais sobre o estado atual do arquivo, permitindo que os desenvolvedores gerenciem melhor os recursos do sistema.

Saber quando um arquivo está aberto ou fechado, por exemplo, ajuda a prevenir erros comuns, como tentativas de acesso a um arquivo já fechado, garantindo a integridade dos dados e a estabilidade do aplicativo.

O objeto do tipo arquivo contém alguns atributos importantes, como name, mode e closed.

### Fechando um arquivo

Após realizar a operação desejada no arquivo, precisamos liberá-lo. Para isso, utilizamos o método `close()`, que libera a memória alocada pelo interpretador e o uso do arquivo por outros programas, por exemplo.

### Lendo o conteúdo de um arquivo

Agora que já sabemos abrir e fechar um arquivo, vamos ver as formas de ler seu conteúdo.

O Python disponibiliza os seguintes métodos para leitura do conteúdo de um arquivo-texto:

- `read()` - Retorna todo o conteúdo de um arquivo como uma única string.
- `readline()` - Retorna uma linha de arquivo, incluindo caracteres de final (\n ou \r\n), e avança o cursor para a próxima.
- `readlines()` - Retorna uma lista em que cada item da lista é uma linha do arquivo.

#### Atenção!
Todos os três métodos apresentados aceitam como parâmetro a quantidade de bytes que desejamos ler.

O valor padrão para esse parâmetro é -1, o que corresponde a todo o arquivo.

### Escrevendo conteúdo em um arquivo

Confira agora como escrever conteúdo em um arquivo a partir da função `open`.

A primeira modificação é alterar o modo de acesso ao arquivo. Para escrita de texto, podemos utilizar o modo w (write) ou o modo (append), a seguir:

 - O modo **w** abre o arquivo para escrita, truncando o arquivo em primeiro lugar. Caso ele não exista, será criado um.
 - O modo **a** abre o arquivo para escrita, acrescentando conteúdo ao final dele, caso ele exista; do contrário, será criado um arquivo

O Python disponibiliza dois métodos para escrita de conteúdo em um arquivo texto, para o modo w e para o modo a. Os métodos write e writelines são descritos abaixo:

- `write` (texto): Escreve todo o conteúdo passado como parâmetro no arquivo.
- `writelines` (iterável): Escreve cada item do iterável (exemplo: lista) no arquivo.

Fique atento às seguintes orientações:
- O Python não insere quebra de linha ('\n') entre os elementos da lista. Precisamos fazer isso manualmente!
- Como o modo w trunca o arquivo, ou seja, remove todo o conteúdo do arquivo, caso ele exista, podemos executar esses scripts repetidas vezes e, ainda assim, o resultado será sempre o mesmo.

### Boas práticas

Ao lidar com arquivos, devemos utilizar a palavra reservada `with`, disponibilizada pelo Python. Ele garante que o arquivo será fechado adequadamente após utilizarmos o arquivo, não sendo necessário chamar o método close explicitamente. A sintaxe de utilização do `with` é:

`with open(caminho, modo) as nome: (seu código indentado)`

Iniciamos com a palavra reservada `with`, seguida da função `open`, a palavra reservada as, um nome de variável que receberá o objeto do tipo arquivo e dois pontos. Todo o código indentado posteriormente está dentro do conotexto do `with`, no qual o arquivo referenciado pela variável nome estará disponível.

---
## 3. Manipulando arquivo-texto em Python

Manipular arquivos de texto em Python permite a automação de tarefas rotineiras, como leitura, escrita e processamento de dados. Essa prática é importante para o desenvolvimento de scripts que gerenciam logs, processam grandes volumes de dados ou geram relatórios.

Além disso, compreender como manipular esses arquivos eficientemente contribui para a criação de aplicativos mais robustas e escaláveis, garantindo melhor gestão e organização das informações.

### Objetivo

A ideia é desenvolver um programa em Python que permita a captura de texto via console, no qual um editor pode inserir trechos de textos recebidos dos autores. O programa deve salvar esses trechos em um arquivo de texto, ler o arquivo, converter todo o texto para letras maiúsculas para padronizar a formatação e finalmente sobrescrever o arquivo original com o texto formatado. Esse processo facilitará a revisão preliminar antes da edição final.

Passos esperados:

- Captura de dados - o programa deve solicitar ao usuário que insira várias frases ou parágrafos pelo console.
- Criação e armazenamento - o texto inserido deve ser salvo em um arquivo chamado meu_arquivo.txt.
- Manipulação do arquivo - o programa deve abrir o arquivo salvo, ler o conteúdo e converter todas as letras para maiúsculas.
- Sobrescrever o arquivo original - após a manipulação, o texto alterado deve ser usado para sobrescrever o arquivo original, garantindo que o arquivo contenha apenas o texto formatado.

### Captura dados

- O script inicia com uma mensagem para o usuário, solicitando que ele digite frases e termine digitando sair quando quiser finalizar
- Um loop `while True` é usado para receber continuamente as entradas do usuário através da função `input()`. Cada entrada é adicionada a uma lista chamada frases.
- O loop é interrompido (break) quando o usuário digita sair, verificado após cada entrada com o método.lower() para garantir a comparação seja insensível a maiúsculas e minúsculas.

### Cria e armazena o arquivo

- Após o término da entrada de dados, o script abre (ou cria, se não existir) um arquivo chamado meu_arquivo.txt no modo de escrita (w) usando a instrução `with open(...) as arquivo`
- Dentro desse bloco, o script escreve cada frase armazenada na lista frases no arquivo. Cada frase é seguida por uma quebra de linha \n.

### Lê e manipula o arquivo

- Uma vez que o arquivo é criado, o script procede para abrir o mesmo arquivo, agora no modo de leitura (r).
- O conteúdo do arquivo é lido linha por linha. Cada linha é despojada de espaços extras e quebras de linha com .strip() e convertida para letras maiúsculas com .upper().
- As linhas modificadas são armazenadas em uma nova lista chamada dados_modificados.

### Sobrescreve o arquivo original

- O arquivo meu_arquivo.txt é novamente aberto, dessa vez, no modo de escrita (w), o que trunca o arquivo a zero antes de começar a escrever.
- O script então escreve cada linha da lista dados_modificados de volta ao arquivo, cada uma terminando com uma quebra de linha \n.
### Confirma a conclusão

- Após a reescrita, uma mensagem é impressa para informar que o arquivo foi sobrescrito com os dados modificados.

É importante considerar o seguinte:
- O uso do contexto with para manipulação de arquivos é uma prática recomendada porque garante que o arquivo seja fechado corretamente após as operações, mesmo se uma execeção ocorrer durante o processo.
- A conversão de todas as entradas para maiúsculas é um exemplo de normalização de dados, útil em muitos contextos de processamento de texto para garantir consistência.

---
## 4. Lidando com dados binários em arquivo com Python

Arquivos binários são usados para armazenar dados de forma compacta e eficiente, incluindo imagens, vídeos, áudios, e arquivos executáveis. Ao manipular arquivos binários, você pode realizar operações de leitura e escrita de dados em baixo nível, possibilitando a criação de aplicações que interagem diretamente com o hardware ou sistemas legados.
