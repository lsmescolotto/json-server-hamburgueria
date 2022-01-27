# URL base

https://entrega-hamburgueria-kenzie.herokuapp.com/

# Endpoints

A API tem 7 (sete) endpoints, que se referem a login, cadastro, exibição dos produtos, pesquisa de produtos, exibição do carrinho de produtos e deletar produtos do carrinho.

# Rotas que não precisam de autenticação

# Cadastro de usuário

POST /register - FORMATO DA REQUISIÇÃO

{
"name": "Jane Doe",
"email": "janedoe@email.com",
"password": "123456",
}

Dando tudo certo, a resposta terá esse formato:

POST /register - FORMATO DA RESPOSTA - STATUS 201

{
"accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6ImphbmVkb2VAbWFpbC5jb20iLCJpYXQiOjE2NDMyNTAwMDAsImV4cCI6MTY0MzI1MzYwMCwic3ViIjoiMyJ9.z90xWRIE7pfKRsw-YqqqUtRxBZGtBPgSZ63yqW04qSc",
"user": {
"email": "janedoe@mail.com",
"name": "Jane Doe",
"id": 3
}
}

# Login

POST /login - FORMATO DA REQUISIÇÃO

{
"email": "janedoe@email.com",
"password": "123456",
}

Dando tudo certo, a resposta terá esse formato:
POST /login - FORMATO DA RESPOSTA - STATUS 201

{
"accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6ImphbmVkb2VAbWFpbC5jb20iLCJpYXQiOjE2NDMyNTAwMDAsImV4cCI6MTY0MzI1MzYwMCwic3ViIjoiMyJ9.z90xWRIE7pfKRsw-YqqqUtRxBZGtBPgSZ63yqW04qSc",
"user": {
"email": "janedoe@mail.com",
"name": "Jane Doe",
"id": 3
}
}

# Listar produtos

GET /products - FORMATO DA RESPOSTA - STATUS 200
[
{
"id": 1,
"name": "Hamburguer",
"category": "Sanduíches",
"price": 14,
"img": "https://i.ibb.co/fpVHnZL/hamburguer.png"
},
{
"id": 2,
"name": "X-Burguer",
"category": "Sanduíches",
"price": 16,
"img": "https://i.ibb.co/djbw6LV/x-burgue.png"
},
{
"id": 3,
"name": "Big Kenzie",
"category": "Sanduíches",
"price": 18,
"img": "https://i.ibb.co/FYBKCwn/big-kenzie.png"
},
{
"id": 4,
"name": "Fanta Guaraná",
"category": "Bebidas",
"price": 5,
"img": "https://i.ibb.co/cCjqmPM/fanta-guarana.png"
},
{
"id": 5,
"name": "Coca",
"category": "Bebidas",
"price": 4.99,
"img": "https://i.ibb.co/fxCGP7k/coca-cola.png"
},
{
"id": 6,
"name": "Fanta",
"category": "Bebidas",
"price": 4.99,
"img": "https://i.ibb.co/QNb3DJJ/milkshake-ovomaltine.png"
}
]

# Pesquisar produtos

GET /products?Propriedade=NomeDoProduto - FORMATO DA REQUISIÇÃO

/products?name=Hamburguer

Dando tudo certo, a resposta terá esse formato:
FORMATO DA RESPOSTA - STATUS 200
[
{
"id": 1,
"name": "Hamburguer",
"category": "Sanduíches",
"price": 14,
"img": "https://i.ibb.co/fpVHnZL/hamburguer.png"
}
]

# Rotas que precisam de autorização

Rotas que necessitam de autorização devem ter no cabeçalho da requisição, o token no campo "Authotization":
Authorization: Bearer {token}

# Adicionar produtos ao carrinho

POST /cart - FORMATO DA REQUISIÇÃO
Além do token de autorização e dos dados do produto, é necessário informar a id do usuário.
{
"id": 1,
"name": "Hamburguer",
"category": "Sanduíches",
"price": 14,
"img": "https://i.ibb.co/fpVHnZL/hamburguer.png",
"userId": 2
}

Dando tudo certo, a resposta terá esse formato:
FORMATO DA RESPOSTA - STATUS 201
{
"id": 1,
"name": "Hamburguer",
"category": "Sanduíches",
"price": 14,
"img": "https://i.ibb.co/fpVHnZL/hamburguer.png",
"userId": 2
}

# Listar produtos do carrinho

GET /cart - FORMATO DA RESPOSTA - STATUS 200
[
{
"id": 1,
"name": "Hamburguer",
"category": "Sanduíches",
"price": 14,
"img": "https://i.ibb.co/fpVHnZL/hamburguer.png"
}
]

# Deletar produtos do carrinho

DELETE /products/IdDoProduto - FORMATO DA REQUISIÇÃO

/products/1

Dando tudo certo, a resposta terá esse formato:
FORMATO DA RESPOSTA - STATUS 200
{}
