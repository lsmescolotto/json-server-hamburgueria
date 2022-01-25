# URL base

https://atividade-json-server-base.herokuapp.com/

# Endpoints

A API tem 6 (seis) endpoints, que se referem a login, cadastro, cadastro de livros, cadastro de livros lidos e listagens dos livros.

# Rotas que não precisam de autenticação

# Cadastro de usuário

POST /register - FORMATO DA REQUISIÇÃO

[
{
"email": "janedoe@email.com",
"password": "123456",
}
]
Dando tudo certo, a resposta terá esse formato:

POST /register - FORMATO DA RESPOSTA - STATUS 201
[
{
"accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6IkxPUE5NQGdtYWlsLmNvbSIsImlhdCI6MTY0MjE5NDgyMCwiZXhwIjoxNjQyMTk4NDIwLCJzdWIiOiIyIn0.Ir5sZiUBnIecrjDv4_xGExtNE0mG-rWoJgBbj9xZ3IQ",
"user": {
"email": "janedoe@email.com",
"id": 2
}
}

]

# Login

POST /login - FORMATO DA REQUISIÇÃO
[
{
"email": "janedoe@email.com",
"password": "123456",
}
]

Dando tudo certo, a resposta terá esse formato:

POST /login - FORMATO DA RESPOSTA - STATUS 201
[
{
"accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6IkxPUE5NQGdtYWlsLmNvbSIsImlhdCI6MTY0MjE5NjQ5NiwiZXhwIjoxNjQyMjAwMDk2LCJzdWIiOiIyIn0.JEweib0sTlmoYIinzHKd0yU6SNdpHm5qWem_uPJKKEk",
"user":
{
"email": "janedoe@email.com",
"password": "123456",
}
}
]

# Rotas que precisam de autorização

Rotas que necessitam de autorização devem ter no cabeçalho da requisição, o token no campo "Authotization":
Authorization: Bearer {token}
