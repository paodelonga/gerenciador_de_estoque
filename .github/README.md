Objetivo deste desafio é criar uma API simples para gerenciar o estoque de um almoxarifado.

## Requisitos

- A API deve permitir operações básicas como cadastro, listagem, atualização e exclusãode produtos.
- Para fins de organização e identidade todas as rotas devem pertencer ao caminho `/almo-sys`
- Realização de consulta por atributos em comum dos produtos
- Todos os produtos em estoque possuem um nome, código númerico para identificação, descrição, um
  valor monetario por unidade e um campo para especificações aonde informações não obrigatorias como "Importante", "Caracteristicas" ou "Dimensões e Peso" serão preenchidas.
- O atributo mandatorio e de identificação é o código numerico, que deve ser unico para cada produto
- A atualização de um produto deve manter o seu código númerico intocavel
- Você é responsável por identificar e implementar as validações para todas as validações
