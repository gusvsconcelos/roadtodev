# **Reconhecer casos de uso por meio de especificações textuais**

## Especificação e Formatos de Casos de Uso

==A **descrição textual** de casos de uso complementa a representação gráfica (Diagrama de Casos de Uso) e é essencial para a elaboração de outros modelos durante o desenvolvimento, como o **Modelo de Classes** e o **Diagrama de Sequência**.== Embora a UML não forneça um padrão formal para essa descrição, diversos formatos são utilizados na prática, dependendo das necessidades do projeto ou da empresa.

## Formatos Comuns de Especificação

Os casos de uso podem ser descritos em diferentes **formatos narrativos**, todos com o objetivo de representar a interação entre os atores e o sistema de maneira clara:

1. **Formato Contínuo**: Um texto narrativo fluido, onde a sequência de ações é descrita de forma contínua.
   - Exemplo: *O Cliente insere o cartão no caixa eletrônico, o sistema solicita a senha, o cliente digita a senha, e assim por diante*.

2. **Formato Numerado**: A descrição é feita por meio de uma sequência de passos numerados, facilitando a leitura e a compreensão.
   - Exemplo: *1. O Cliente insere o cartão. 2. O Sistema solicita a senha...*

3. **Formato Tabular**: Uma tabela que organiza as interações entre o ator e o sistema em colunas separadas.
   - Exemplo:

| Cliente       | Sistema         |
| ------------- | --------------- |
| Insere cartão | Solicitar senha |
| Digita senha  | Valida senha    |

## Cenário Principal e Cenários Alternativos

O **cenário principal** descreve o fluxo normal de eventos em que o caso de uso segue sem imprevistos. Já os **cenários alternativos** ou **cenários de exceção** são utilizados para descrever fluxos alternativos ou problemas que podem ocorrer durante a execução do caso de uso.

- **Cenário Principal**: Fluxo bem-sucedido, onde todas as ações são realizadas conforme o esperado.
- **Cenários Alternativos**: Fluxos que fogem do esperado, como o cliente digitar a senha errada, ==o que exigiria uma especificação para tratar esse erro.==

## Estrutura de Especificação de Casos de Uso

==Como a UML não define um padrão para essa especificação, as equipes podem criar seus próprios modelos.== Um exemplo comum de estrutura adaptada de Bezerra (2015) inclui os seguintes campos:

1. **Identificador**: Código único para rastrear o caso de uso.
2. **Nome**: Uma frase verbal que descreve a ação principal (ex.: "Criar conta corrente").
3. **Objetivo**: O objetivo do ator no caso de uso.
4. **Ator Primário**: Aquele que inicia o caso de uso.
5. **Atores Secundários**: Outros atores envolvidos.
6. **Pré-condições**: Condições que devem ser verdadeiras antes do início do caso de uso.
7. **Cenário Principal**: A sequência normal de eventos.
8. **Cenários Alternativos e de Exceção**: Sequências que descrevem fluxos alternativos.
9. **Pós-condições**: O estado do sistema após a execução do caso de uso.
10. **Regras de Negócio**: Regras que afetam a execução do caso de uso.

## Casos de Uso com Inclusão e Extensão

==Em casos de uso que envolvem **inclusão** ou **extensão**, a especificação normalmente faz referência ao caso de uso incluído ou estendido==, descrevendo claramente o ponto onde ocorre essa relação.