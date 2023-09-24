# API de Games 
Esta API é utilizada ajudar e compreender os endpoints 
## Endpoints
### GET /games
Esse endpoint é responsável por retornar a listagem de todos os games cadastrados no banco de dados.
#### Parâmetros
Nenhum
#### Respostas
##### OK! 200
Caso essa essa resposta aconteça, você vai receber a lista de games.
Exemplo de resposta: 
```
[
    {
        "id": 23,
        "title": "Call of duty",
        "year": 2019,
        "price": 60
    },
    {
        "id": 65,
        "title": "Sea of thieves",
        "year": 2018,
        "price": 40
    }
]
```
##### Falha na autenticação! 401
Caso essa resposta aconteça, isso significa cque aconteceu alguma falha no processo de requisição da autenticação. Motivos: Token inválidos, token expirado.
Exemplo de resposta:
```
{
    "err": "Token inválido"
}
```

==================================================

### POST /auth
Esse endpoint é responsável por fazer o processo de login.
#### Parâmetros
email: E-mail do usuário cadastrado no sistema

password: Senha do usuário cadastrado no sistema, com aquele determinado e-mail
#### Respostas
##### OK! 200
Caso essa essa resposta aconteça, você vai receber o token JWT para conseguir acessar endpoints protegidos na API.
Exemplo de resposta: 
```
{
    "token": "eyJhbGciOiuIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZoI6MjAsImVtYWlsIjoiZGltYXNAZ21haWwuY29tIiwiaWF0IjoxNjk1NTk1OTcwLCJleHAiOjE2OTU3Njg3MzB9.pbnFwB8171RxCCHN9c1Z6ak9AzvSkREV74-ZgPMyUaM"
}
```
##### Falha na autenticação! 400
Caso essa resposta aconteça, isso significa que aconteceu alguma falha no processo de requisição da autenticação. 
Motivos: Problemas no servidor ao  tentar gerar o token de acesso ou o email não ser informado.
Exemplo de resposta:
```
{
    "err": "Falha interna"
}
```
ou
```
{
    "err": "O E-mail enviado não existe na base de dados"
}
```
##### Falha na autenticação! 401
Caso essa resposta aconteça, isso significa cque aconteceu alguma falha no processo de requisição da autenticação. 
Motivos: Senha ou email incorretos.
Exemplo de resposta:
```
{
    "err": "Credenciais inválidas"
}
```
##### Falha na autenticação! 404
Caso essa resposta aconteça, isso significa cque aconteceu alguma falha no processo de requisição da autenticação. 
Motivos: Senha ou email incorretos.
Exemplo de resposta:
```
{
    "err": "Credenciais inválidas"
}
```


