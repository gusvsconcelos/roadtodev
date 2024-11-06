# **Revisar o diagrama de classes da análise no projeto de sistema**

## Diagrama de Classes de Projeto

- **Objetivo**: ==Representar os dados necessários para a construção do sistema==, incluindo classes, atributos, operações, métodos, interfaces e pacotes.
- **Diferença entre análise e projeto**: ==Na análise, foca-se no domínio do problema; no projeto, foca-se na solução do problema==, dando importância a aspectos relacionados à implementação de software.

## Especificação de Atributos

==A sintaxe completa de um atributo é mais detalhada que na fase de análise== e inclui visibilidade, nome, tipo, valor inicial e multiplicidade.

### *Visibilidade*
 Determina o nível de acesso ao atributo
 
 **Pode ser:**
  - **Público (`+`)**
  - **Protegido (`#`)**
  - **Privado (`-`)**
  - **De pacote (`~`)**

### *Atributos derivados*
Indicado por uma barra inclinada (`/`), ==são atributos calculados a partir de outros==, como a idade derivada da data de nascimento.

### *Multiplicidade*
==Define a quantidade de valores que um atributo pode ter==, variando de `0..1` (opcional) a `1..*` (obrigatório e muitos).

## Especificação de Operações/Métodos

==A operação também possui visibilidade, nome, lista de parâmetros e tipo de retorno.== Os parâmetros podem ter direção de entrada (`IN`), saída (`OUT`) ou ambos (`INOUT`).

## Especificação de Associações

As associações entre classes representam relacionamentos e podem ser unidirecionais ou bidirecionais. ==A navegabilidade é importante, pois associações bidirecionais aumentam o acoplamento, o que pode dificultar a manutenção.==

### *Dependências*
Uma classe pode depender de outra por diversos motivos, como atributos, variáveis locais, globais ou parâmetros. ==Dependências são representadas com setas tracejadas.==

## Classes Persistentes e Transientes

- **Persistentes**: Seus objetos são preservados após o uso do sistema.
- **Transientes**: São destruídos ao final da execução.

## Classes de Interface

Especificam serviços sem definir a implementação, ==sendo utilizadas para definir como classes externas colaboram com o sistema.==

## Navegabilidade de Associações

Associações podem ser refinadas de bidirecionais para unidirecionais durante o projeto para reduzir o acoplamento entre as classes e melhorar a modularização.