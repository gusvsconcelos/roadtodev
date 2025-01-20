# **Esquema Red Green Blue (RGB)**

## Representação de cores em computadores

O esquema de cores RGB é amplamente utilizado em telas digitais, como monitores, TVs e smartphones. ==Ele forma a base para a exibição de cores nesses dispositivos, combinando luz em diferentes intensidades.==

---
## O que é o RGB?

RGB é um modelo de cores aditivo baseado em três cores primárias da luz.

- **R**: Red (vermelho)
- **G**: Green (verde)
- **B**: Blue (azul)

Quando essas cores são combinadas em diferentes intensidades, elas criam um espectro de milhões de cores.

---
## Como funciona o RGB?

O modelo é aditivo, ou seja, as cores são criadas ao adicionar luz. A combinação máxima (255, 255, 255) cria o branco, enquanto a ausência de luz (0, 0, 0) resulta em preto. ==Valores intermediários entre 0 e 255 para cada canal produzem diferentes cores.==

- Vermelho puro **(255, 0, 0)**
- Verde puro **(0, 255, 0)**
- Azul puro **(0, 0, 255)**
- Amarelo **(255, 255, 0)**
- Cinza médio **(128, 128, 128)**

---
## Aplicações para o RGB

- Monitores e telas digitais
- Design gráfico e web
- Programação

---
## RGB em Profundidade de Cor

A profundidade de cor refere-se à quantidade de informações que cada canal pode conter.

- Com 8 bits por canal (24 bits no total), ==temos 256 valores para cada cor.==
- O total de combinações possíveis é **256 x 256 x 256 = 16.777.216** cores.

---
## RGB vs. Outros Modelos de Cor

**RGB x CMYK**
- RGB é aditivo, usado em dispositivos emissores de luz.
- CMYK é subtrativo, usado em impressão

**RGB x HSL/HSV**
- HSL (Hue, Saturation, Lightness) e HSV (Hue, Saturation, Value) são variações que representam as cores de forma intuitiva para o design

---
## Limitações do RGB

- Gamut Limitado: O RGB não consegue representar todas as cores visíveis ao olho humano.
- Dependência de dispositivo: A aparência das cores pode variar de uma tela para outra devido às diferenças de calibração e tecnologia.

---
## RGB e Hexadecimal

O modelo RGB é frequentemente representado no formato hexadecimal em desenvolvimento web.

Cada canal é convertido em um número hexadecimal (00 a FF).
- RGB(255, 0, 0) = `#FF0000`
- RGB(0, 255, 0)  = `#00FF00`