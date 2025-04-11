# **Criação de aplicação GUI**

## 1. Biblioteca Tkinter

**Tkinter** é a biblioteca padrão do Python para desenvolvimento de GUIs. Com sua interface orientada a objetos, ela facilita a criação de aplicações visuais interativas.

==É compatível com múltiplas plataformas, tornando-a uma excelente opção tanto para iniciantes quanto para desenvolvedores experientes.==

### Etapas para Criar Aplicações com Tkinter

- **Importar a biblioteca**:
    
    ```python
    import tkinter as tk
    ```
    
- **Criar a janela principal**:
    
    ```python
    janela = tk.Tk()
    janela.title("Minha Aplicação Tkinter")
    ```
    
- **Adicionar widgets**: Utilize componentes como botões, rótulos, caixas de entrada, etc.
    
    ```python
    rotulo = tk.Label(janela, text="Olá, Tkinter!")
    rotulo.pack()
    ```
    
- **Entrar no loop de eventos**:
    
    ```python
    janela.mainloop()
    ```

### Exemplo Básico

Aqui está um exemplo funcional que exibe uma janela simples com um rótulo:

```python
import tkinter as tk

# Criar janela principal
janela = tk.Tk()
janela.title("Exemplo Básico")

# Adicionar widget
rotulo = tk.Label(janela, text="Bem-vindo ao Tkinter!")
rotulo.pack()

# Iniciar loop de eventos
janela.mainloop()
```

**Saída**: Uma janela com o texto "Bem-vindo ao Tkinter!".

### Widgets Disponíveis no Tkinter

Tkinter oferece uma ampla variedade de componentes (widgets) para construir interfaces interativas:

- **Botão** (Button)
- **Canvas**
- **Entrada de texto** (Entry)
- **Rótulo** (Label)
- **Caixa de listagem** (Listbox)
- **Botão de rádio** (Radiobutton)
- **Barra de rolagem** (Scrollbar)
- **Texto** (Text)

### Customização

Cada widget possui propriedades que permitem personalizar:

- **Tamanho**: Definir largura e altura do widget.
- **Fonte**: Alterar estilo, cor e tamanho do texto.
- **Cor**: Configurar a aparência visual do widget.

---
## 2. Exemplos de aplicações GUI