# **Esquematização de uma Aplicação RAD com Python**

## 1. Requisitos do Sistema

### Propósito

Criar um **Sistema de Cadastro de Notas de Alunos**, que permita:

- Cadastro de nome e notas dos alunos.
- Cálculo da média e situação (Aprovado, Recuperação, Reprovado).
- Exportação e leitura de dados via **planilha Excel (.xlsx)**.

### Escopo

Sistema simples, funcional e didático, voltado para pequenas escolas.

### Interfaces

| **Tipo**              | **Detalhes**                                     |
| --------------------- | ------------------------------------------------ |
| Sistema Operacional   | Windows                                          |
| Interface de Usuário  | GUI com botões, campos de texto e tabela (grade) |
| Interface de Software | Importação/exportação com MS Excel via `pandas`  |

### Requisitos Funcionais

- Inserir dados: nome, nota1, nota2.
- Exibir média e situação.
- Gravar e ler de uma planilha Excel.

---
## 2. Modelagem de Negócio

### Casos de Uso

- **Atores**: Funcionários e Alunos.
- **Funcionário**: cadastra nome e notas.
- **Aluno**: visualiza situação escolar.

---
## 3. Modelagem de Dados

| **Campo** | **Tipo** |
| --------- | -------- |
| Aluno     | Texto    |
| Nota1     | Decimal  |
| Nota2     | Decimal  |
| Média     | Decimal  |
| Situação  | Texto    |

Armazenamento: **planilha Excel (.xlsx)** usando `pandas`.

---
## 4. Design da Interface com o Usuário (UI)

### Biblioteca Usada: `Tkinter`

| **Componente**    | **Código Exemplo**                       |
| ----------------- | ---------------------------------------- |
| Janela            | `janela = tk.Tk()`                       |
| Rótulo (Label)    | `tk.Label(janela, text="Nome do Aluno")` |
| Entrada (Entry)   | `tk.Entry()`                             |
| Botão             | `tk.Button(..., command=...)`            |
| Tabela (Treeview) | `ttk.Treeview()`                         |
| Scrollbar         | `ttk.Scrollbar()`                        |

---
## 5. Detalhes de Implementação

### Pacotes Importados

```python
import tkinter as tk
from tkinter import ttk
import pandas as pd
```

### Teste de instalação do Tkinter

```python
import tkinter
tkinter._test()
```

---
## 6. Estrutura do Código

### Ciclo de Vida da Interface

```python
janela = tk.Tk()
app = SistemaCadastro(janela)
janela.title("Cadastro de Notas")
janela.geometry("800x400")
janela.mainloop()
```

### Classe Principal (POO)

```python
class SistemaCadastro:
    def __init__(self, win):
        ...
	        self.btnCalcular = tk.Button(
	        win,
	        text="Calcular Média",
	        command=self.fCalcularMedia
	        )
        ...
        self.carregarDadosIniciais()
```

### Carregar dados de planilha Excel

```python
try:
    dados = pd.read_excel("arquivo.xlsx")
    for i in range(len(dados)):
        self.treeview.insert("", "end", values=(...))
except:
    print("Ainda não existem dados para carregar.")
```

### Cálculo da Média e Situação

```python
def fCalcularMedia(self):
    try:
        nome = self.entryNome.get()
        nota1 = float(self.entryNota1.get())
        nota2 = float(self.entryNota2.get())
        media, situacao = self.fVerificarSituacao(nota1, nota2)
        ...
        self.fSalvarDados(nome, nota1, nota2, media, situacao)
    except:
        print("Entre com dados válidos.")
    finally:
        self.limparCampos()

def fVerificarSituacao(self, nota1, nota2):
    media = (nota1 + nota2) / 2
    if media >= 7:
        situacao = "Aprovado"
    elif media >= 5:
        situacao = "Recuperação"
    else:
        situacao = "Reprovado"
    return media, situacao
```

---

## 7. Pilares do Código

| **Conceito**           | **Aplicação Prática**                       |
| ---------------------- | ------------------------------------------- |
| `self`                 | Referência à instância (POO)                |
| `try-except-finally`   | Tratamento robusto de exceções              |
| `pandas.read_excel()`  | Importação de datasets                      |
| `ttk.Treeview`         | Visualização dos dados                      |
| Reutilização de código | Métodos separados para clareza e manutenção |

---
## 8. Evoluções Possíveis (Iterações RAD)

- 🔐 Tela de Login (usuários com permissões distintas).
- 🛢️ Uso de Banco de Dados ao invés de planilha.
- 📊 Dashboards com estatísticas de desempenho.
- 🌐 Versão Web com Flask ou Django.

---
## Conclusão

A implementação RAD com Python permite:

- **Entrega rápida**
- **Feedback constante**
- **Flexibilidade para evoluir**

Mas depende fortemente de:

- 💪 Profissionais qualificados.
- 🔄 Comunicação constante com usuários.
- ✅ Planejamento bem definido.