## ✅ RESUMO PARA PROVAS – AUTOMATIZAÇÃO DE TAREFAS NO LINUX

---

### 🔹 VISÃO GERAL

- Automatização no Linux usa:
    
    - **CRON**: agendamento de tarefas.
    - **Shell Scripts (bash)**: sequências de comandos executados automaticamente.
        
- Importância:
    
    - Reduz trabalho manual repetitivo
    - Evita erros humanos
    - Permite execução sem interação

---

### 🔹 MÓDULO 1 – AGENDAMENTO COM CRON

#### O que é o CRON:

- Ferramenta nativa do Unix/Linux para **agendar tarefas**.
- Multiusuário: cada usuário possui sua própria crontab.
- Executa comandos automaticamente em dias/horários definidos.

#### Configuração:

- Comando para editar: `crontab -e`
- Cada linha tem **6 campos**:
    
    1. Minuto (0-59)
    2. Hora (0-23)
    3. Dia do mês (1-31)
    4. Mês (1-12 ou jan-dez)
    5. Dia da semana (0=domingo a 6=sábado)
    6. Comando a ser executado

#### Exemplos:

- `30 17 * * * /bin/comando` → Executa às 17h30 todos os dias
- `0 20 * * * tar -cfz /tmp/backup.tar.gz /home/bob` → Backup diário
- `*/10 * * * *` → Executa a cada 10 minutos
- `0 8-17 * * 1-5` → Executa das 8h às 17h, de segunda a sexta

#### Cuidados:

- Não usar `sudo` em crontab de usuário
- Atenção às permissões dos arquivos e caminhos absolutos

#### CRON global:

- Arquivo: `/etc/crontab`
- Inclui campo extra com o nome do usuário:
    
    - Ex: `30 10 * * * root /bin/comando`
        
- Diretórios especiais:
    
    - `/etc/cron.hourly`, `cron.daily`, `cron.weekly`, `cron.monthly`

#### Saída de logs:

- Redirecionar saída: `>> /caminho/arquivo.log`

---

### 🔹 MÓDULO 2 – SHELL SCRIPT BÁSICO

#### O que é um Shell Script:

- Arquivo texto contendo comandos sequenciais para automação
- Interpretado diretamente pelo **bash** (sem compilação)

#### Início obrigatório:

- Palavra mágica: `#!/bin/bash`

#### Permissões:

- Tornar executável: `chmod u+x script.sh`
- Executar com caminho: `./script.sh`

#### Comandos úteis:

- `echo` → imprime texto
- `date` → mostra data/hora
- `sleep` → pausa execução (segundos)
- `read` → recebe entrada do usuário
- `clear` → limpa tela
- `exit` → encerra script com código de retorno

#### Interpolando comandos:

- `echo "Data: $(date +%d/%m/%Y)"`
    
---

### 🔹 MÓDULO 3 – VARIÁVEIS E CONDIÇÕES

#### Variáveis:

- Definição: `VAR=valor`
- Uso: `$VAR`
- Case-sensitive
- Textos com espaço: usar aspas

#### Entrada interativa:

- `read VAR` → armazena entrada em VAR

#### Parâmetros:

- Passados na execução: `./script.sh valor1 valor2`
- Acessados como `$0`, `$1`, `$2`, ..., `${10}`

#### Condicional `if`:

```bash
if [[ CONDICAO ]]; then
  comandos
else
  outros_comandos
fi
```

#### Comparadores numéricos:

- `-eq`: igual
- `-ne`: diferente
- `-gt`: maior
- `-ge`: maior ou igual
- `-lt`: menor
- `-le`: menor ou igual

#### Strings:

- `=`: igual
- `!=`: diferente
- `-z`: vazia
- `-n`: não vazia

#### Expressões regulares:

- `[[ $VAR =~ ^[0-9]{3}$ ]]` → número com 3 dígitos

#### Operações:

- Inteiros: `(( VAR=10+5 ))` ou `$(( 10+5 ))`
- Float: `echo "scale=2; 10/3" | bc`

---

### 🔹 MÓDULO 4 – ESTRUTURAS DE REPETIÇÃO

#### While

```bash
while [[ CONDICAO ]]; do
  comandos
  (( i++ ))
done
```

#### For

```bash
for var in lista; do
  comandos
done
```

- Ex: `for arq in *` percorre arquivos do diretório

#### Controle de fluxo:

- `break`: interrompe o loop
- `continue`: pula para a próxima iteração

#### Leitura de arquivos

- `VAR=$(<arquivo.txt)` → carrega conteúdo para variável

---

## 🖊️ QUESTÕES COMENTADAS – CRON E SHELL SCRIPT

**1.** Qual comando é usado para editar a tabela de agendamentos do usuário?

A) cron -e  
B) crontab -e  
C) cron edit  
D) edit-cron  
E) schedule -cron

✅ **Gabarito: B**

> O comando `crontab -e` abre a tabela do usuário atual para edição.

---

**2.** Qual das opções representa um agendamento válido que executa uma tarefa todos os dias às 22h?

A) 0 22 * * * /bin/script.sh  
B) * 22 * * * /bin/script.sh  
C) 22 0 * * * /bin/script.sh  
D) * * 22 * * /bin/script.sh  
E) 0 10 * * * /bin/script.sh

✅ **Gabarito: A**

> `0 22 * * *` significa 22:00 todos os dias.

---

**3.** Em um script bash, o comando `echo "Resultado: $((2+3))"` exibirá:

A) Resultado: 5.0  
B) Resultado: 2+3  
C) Resultado: 5  
D) Erro de sintaxe  
E) 2+3

✅ **Gabarito: C**

> `(( ))` é usado para operações aritméticas de inteiros no bash.

---

**4.** O que faz o seguinte trecho?

```bash
for x in 1 2 3; do
  echo "$x"
done
```

A) Executa infinitamente  
B) Percorre a pasta atual  
C) Exibe os números 1, 2 e 3 em linhas separadas  
D) Soma os números  
E) Compara strings

✅ **Gabarito: C**

> O loop percorre os elementos da lista e imprime um por linha.

---

**5.** Qual alternativa representa o comando correto para fazer um script interativo receber um valor digitado?

A) input A  
B) scanf A  
C) let A  
D) read A  
E) gets A

✅ **Gabarito: D**

> `read` é usado para capturar entrada do usuário no bash.