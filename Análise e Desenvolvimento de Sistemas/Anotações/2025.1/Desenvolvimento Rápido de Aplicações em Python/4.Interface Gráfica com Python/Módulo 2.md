# **Criação de Aplicação GUI com Tkinter**

## 1. Introdução ao Tkinter

**Tkinter** possui sintaxe simples, componentes prontos e suporte nativo à programação orientada a objetos.

- É o framework oficial do Python para interfaces gráficas.

> *🎯 Compatível com várias plataformas. Ideal tanto para iniciantes quanto para projetos profissionais.*

---
## 2. Etapas de Criação com Tkinter

1. **Importar a biblioteca**

```python
import tkinter as tk
```

2. **Criar a janela principal**

```python
janela = tk.Tk()
janela.title("Minha Aplicação Tkinter")
```

3. **Adicionar widgets**

```python
rotulo = tk.Label(janela, text="Olá, Tkinter!")
rotulo.pack()
```

4. **Rodar o loop principal**

```python
janela.mainloop()
```

---
## 3. Exemplo Básico

```python
import tkinter as tk

janela = tk.Tk()
janela.title("Exemplo Básico")

rotulo = tk.Label(janela, text="Bem-vindo ao Tkinter!")
rotulo.pack()

janela.mainloop()
```

> *💡 Este código cria uma janela com o texto “Bem-vindo ao Tkinter!”*

---
## 4. Principais Widgets do Tkinter

Você pode construir qualquer interface visual combinando os widgets abaixo:

- `Label` → Exibe textos.
- `Button` → Executa comandos ao clicar.
- `Entry` → Campo para entrada de texto.
- `Text` → Área de texto multiline.
- `Listbox` → Lista de itens.
- `Radiobutton` → Opção exclusiva.
- `Scrollbar` → Barra de rolagem.
- `Canvas` → Desenhos e formas gráficas.

> *🧩 Cada widget pode ser personalizado para alinhar com o layout e design da aplicação.*

---
## 5. Personalização de Widgets

Todos os componentes podem ser ajustados com argumentos de configuração:

- `width`, `height` → Tamanho.
- `font` → Estilo, tipo e tamanho da fonte.
- `bg`, `fg` → Cor de fundo e texto.
- `padx`, `pady` → Espaçamento interno.

> *🛠️ Customização visual é essencial para criar UIs modernas e agradáveis.*