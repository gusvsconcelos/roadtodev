# **Construir o modelo de casos de uso para um estudo de caso de modelagem de sistemas em UML**

## Diagrama de Casos de Uso - Definições

**Casos de Uso:** Representam as funcionalidades que o sistema deve fornecer.

**Atores:** Elementos externos que interagem com o sistema (ex.: Cliente, Recepção, Operadora de Cartão).

**Relacionamentos:**
 - **Generalização:** Atores ou casos de uso podem herdar comportamentos uns dos outros.
 - **Include:** Um caso de uso obrigatoriamente inclui a execução de outro.
 - **Extend:** Um caso de uso pode ser estendido por outro em situações específicas.

## Estudo de Caso – Diagramas de Casos de Uso

**Requisito Funcional 1 (RF 1):**  
 *"Registrar Reserva", realizado tanto por **Cliente** quanto pela **Recepção**.*
 
 - **Relacionamento:** Atores têm uma relação de **generalização**, pois a Recepção pode executar a função do Cliente.
---
**Requisito Funcional 11 (RF 11):**  
 *A quitação da reserva é feita no **check-out** utilizando o cartão de crédito.*
 
 - **Relacionamento:** "Realizar Check-out" **inclui** o comportamento de "Quitar Reserva", de forma incondicional.
---
**Requisito Funcional III (RF III):**  
 *Reserva feita online gera uma cobrança imediata de uma diária via cartão de crédito.*
 
 - **Relacionamento:** O caso de uso "Registrar Reserva" utiliza o **extend** para incluir "Registrar Cobrança de Diária", um comportamento condicional.

## Empacotamento de Casos de Uso

==Em sistemas mais complexos, é útil organizar casos de uso em **pacotes**. Isso facilita a visualização de módulos e componentes do sistema.== Um exemplo de empacotamento seria organizar casos de uso por atores (ex.: Cliente, Recepção, Operadora de Cartão).

## Descrições de Casos de Uso

==Cada caso de uso também é acompanhado por uma **descrição textual**.== Esses textos detalham as interações entre atores e sistema, como as pré-condições, fluxos principais, fluxos alternativos, fluxos de exceção e regras de negócio.

**Exemplo: "Registrar Reserva"**
- **Atores:** Cliente ou Recepção
- **Pré-condição:** O ator deve estar identificado pelo sistema.
- **Fluxo Principal:** O Cliente ou Recepção seleciona o quarto, e o sistema realiza a reserva.
- **Fluxos Alternativos:** Incluem reservas feitas por telefone e situações de falha no pagamento via cartão.

## Manter Pousada (Caso de Uso Secundário)

==Um caso de uso secundário envolve operações **CRUD** (Criar, Ler, Atualizar, Deletar) para gerenciar os dados da pousada.==

**Fluxo Principal:** O setor administrativo pode inserir, consultar, alterar ou excluir informações de uma pousada.