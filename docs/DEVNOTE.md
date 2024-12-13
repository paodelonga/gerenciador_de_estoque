Objetivo deste desafio é criar uma API simples para gerenciar o estoque de um almoxarifado.

## Requisitos

- A API deve permitir operações básicas como cadastro, listagem, atualização e exclusãode produtos.
- Para fins de organização e identidade todas as rotas devem pertencer ao caminho `/almo-sys`
- Realização de consulta por atributos em comum dos produtos
- Todos os produtos em estoque possuem um nome, código númerico para identificação, descrição, um
  valor monetario por unidade e um campo para especificações aonde informações não obrigatorias como "Importante", "Caracteristicas" ou "Dimensões e Peso" serão preenchidas.
- O atributo mandatorio e de identificação é o código numerico que deve ser unico para cada produto
- A atualização de um produto deve manter o seu código númerico intocavel
- Identificar e implementar as adequadas validações nas operações

# Ditas

### Produto
  - Nome; String;
  - Codigo; Integer;
  - Descricao; String;
  - Valor; Integer;
  - Especificacao; Json (i thk)
    - Importante
    - Caracteristicas
    - Dimensoes e peso
  - Quantidade; Integer

# Darabases

### table: produto
- id: uuid primary
- name: integer
- code: integer unique
- descricao: string
- valor: integer
- especificacao: string

# Fluxs

### Produto
- Cadastrar um produto; CREATE; PUT
- Listar produtos em registro; READ; GET
- Exibir informacoes de um produto; READ; GET
- Atualizar informações de um produto; UPDATE; POST
- Excluir cadastro de um produto; DELETE; DELETE

---

- Cadastrar produto
PUT /product

- Listar produtos
GET /product

- Obter produto
GET /product/{code}

- Atualizar produto
POST /product/{code}

- Excluir
DELETE /product/{code}

# API Things
### Boiler

```
GET localhost:8890/almo-sys/
{}
```

```
POST localhost:8890/almo-sys/
{}
```

```
PUT localhost:8890/almo-sys/
{}
```

```
DELETE localhost:8890/almo-sys/
{}
```

## Rotas

### GET

``` Obter todos os produtos
GET localhost:8890/almo-sys/product
{}
```

``` Obter um produto expecifico
GET localhost:8890/almo-sys/product/{code}
{}
```

### POST

``` Atualizar um produto existente
POST localhost:8890/almo-sys/product/{code}
{}
```

### PUT

``` Registrar um novo produto
PUT localhost:8890/almo-sys/product
{}
```

### DELETE

``` Deletar um produto existente
DELETE localhost:8890/almo-sys/product/{code}
{}
```

---

| Method | Endpoint | Description |
| :--: | :- | :-- |
| POST | /almo-sys/product/{code} | Atualizar um produto existente por codigo numerico |
| GET | /almo-sys/product | Obter todos os produtos |
| GET | /almo-sys/product{code} | Obter um produto expecifico por codigo numerico |
| PUT | /almo-sys/product | Registrar um novo produto |
| DELETE | /almo-sys/product/{code} | Deletar um produto existente por codigo numerico |


# Tips

O produto vai ser cadastrado utilizando um uuid para diferencialo, mas a jogadinha aqui é fazer com que o código
do produto seja um hashcode do uuid, talvez seja uma boa
