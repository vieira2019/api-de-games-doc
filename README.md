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
