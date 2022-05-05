# API de Games
Esta API é utilizada para consumo...
## ENDPOINTS
### GET /games
Esse endpoint é responsável por retornar a listagem de todos os games cadastrados no banco de dados
### PARÂMETROS
Nenhum
### RESPOSTAS
##### OK! 200
Caso essa resposta aconteça você vai receber a listagem de todos os games.

Exemplo de resposta:
```
[
	{
		"id": 23,
		"title": "Call of duty MW",
		"year": 2019,
		"price": 60
	},
	{
		"id": 65,
		"title": "Sea of thieves",
		"year": 2018,
		"price": 40
	},
	{
		"id": 2,
		"title": "Minecraft",
		"year": 2012,
		"price": 20
	}
]
```
##### Falha na autenticação! 401
Caso essa resposta aconteça, isso significa que aconteceu alguma falha durante o processo de autenticação da requisição. 

Motivos: Token inválido, Token expirado.

Exemplo de resposta:
```
{
	"err": "Token inválido!"
}
```
### POST /auth
Esse endpoint é responsável por fazer o processo de login.
### PARÂMETROS
email: E-mail do usuário cadastrado no sistema.

password: senha do usuário cadastrado no sistema.

Exemplo:
```
{
        "email": "testes@teste.com",
	"password": "nodejs<3"
}
```

### RESPOSTAS
##### OK! 200
Caso essa resposta aconteça você vai receber o token JWT para conseguir acessar endpoints protegidos na API.

Exemplo de resposta:
```
{
	"token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MSwiZW1haWwiOiJ0ZXN0ZXNAdGVzdGUuY29tIiwiaWF0IjoxNjUxNzg0ODY3LCJleHAiOjE2NTE5NTc2Njd9.GgZaw8dJgps1tHHgb4v2xuCG-IiFAXh40CzPg3IF5p4"
}
```
##### Falha na autenticação! 401
Caso essa resposta aconteça, isso significa que aconteceu alguma falha durante o processo de autenticação da requisição. 

Motivos: Senha ou e-mail incorretos.

Exemplo de resposta:
```
{err: "Credenciais inválidas!"}
```
