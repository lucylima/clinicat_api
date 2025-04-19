# Clinicat API

Uma API feita para o aplicativo web Clinicat que permite adicionar usuários, pets e consultas no veterinário.

## Sumário
- [Instalação](#instalação)
- [Uso](#uso)
- [Documentação da API](#documentação-da-api)


## Tecnologias usadas

<p align="center">
  <a href="https://skillicons.dev">
    <img src="https://skillicons.dev/icons?i=nodejs,js,express,postgres,prisma" />
  </a>
</p>

## Instalação

1. Clone o repositório
   ```bash
   git clone https://github.com/lucylima/clinicat_api.git
   cd clinicat_api
   ```
   
2.  Instale as dependências
    
    ```bash
    npm install
    ```
    
3.  Defina as variáveis de ambiente
    -   Crie um arquivo chamado `.env`  na raiz do projeto.
    -   Adicione as seguintes variáveis de ambiente:
        ```env
        DATABASE_URL=sua_string_do_banco_de_dados_postgres
        PORT=3000
        ```
        
4.  Inicie o servidor de desenvolvimento e gere 
    
    ```bash
    npm run dev
    ```

## Uso

Inicie o servidor de desenvolvimento:

```bash
npm run dev
```

A API estará disponível em `http://localhost:3000`. Use ferramentas como cURL, Postman ou Insomnia para testar os endpoints da aplicação


## Documentação da API
###  Usuário
| Método | Endpoint  | Descrição                                            | Request Body |
| ------ | --------- | ---------------------------------------------------- | ------------ |
| GET    | /user     | Obtêm um usuário pelo nome de usuário, email e senha | Sim          |
| POST   | /user     | Cria um novo usuário.                                | Sim          |
| PUT    | /user/:id | Edita um usuário pelo id.                            | Sim          |
| DELETE | /user/:id | Remove um usuário pelo id.                           | Não          |
---
###  Pet
| Método | Endpoint | Descrição                        | Request Body |
| ------ | -------- | -------------------------------- | ------------ |
| GET    | /pet     | Pesquisa um pet pelo nome.       | Sim          |
| GET    | /pet/:id | Mostra todos os pets de um dono. | Não          |
| POST   | /pet     | Cria um novo pet.                | Sim          |
| PUT    | /pet     | Edita um pet existente.          | Sim          |
| DELETE | /pet     | Deleta um pet.                   | Sim          |
---
### Consulta
| Método | Endpoint         | Descrição                   | Request Body |
| ------ | ---------------- | --------------------------- | ------------ |
| GET    | /appointment     | Retorna todas as consultas  | Não          |
| POST   | /appointment     | Cria uma nova consulta.     | Sim          |
| PUT    | /appointment/:id | Edita uma consulta pelo id. | Sim          |
| DELETE | /appointment     | Deleta uma consulta         | Sim          |
---

### Corpos da requisição

### Usuário
**POST `/user`**
```json
{
	"name": "Neferpitou",
	"username": "pitou",
	"email": "neferpitou@mail.com",
	"password": "pitou1345",
	"telephone": "71 94565-2456",
	"gender": "undefined"
}
``` 

**GET`/user`**
```json
{
	"username": "pitou",
	"email": "neferpitou@mail.com",
	"password": "pitou1345"
}
``` 

**PUT`/user/:id`**
```json
{
	"name": "Neferpitou",
	"username": "pitou",
	"email": "neferpitou@mail.com",
	"password": "pitou1345",
	"telephone": "71 94565-2456",
	"gender": "undefined"
}
``` 
---

### Pet
**GET`/pet`**
```json
{
	"name": "Pouf",
	"owner": "cm9orztei00010cjs9wt2dg7x" # exemplo de id CUID
}
``` 

**POST`/pet`**
```json
{
	"name": "Pouf",
	"breed": "Dog",
	"owner": "cm9orztei00010cjs9wt2dg7x" 
}
``` 

**PUT`/pet`**
```json
{
	"id": "cm9os8cyk00000cl85wvl1nxv",
	"name": "Pouf",
	"breed": "Dog",
	"owner": "cm9orztei00010cjs9wt2dg7x" 
}
``` 
**DELETE `/pet`**
```json
{
	"name": "Pouf",
	"owner": "cm9orztei00010cjs9wt2dg7x" 
}
``` 
---
### Consulta

**POST`/appointment`**
```json
{
	"pet": "cm9os8cyk00000cl85wvl1nxv",
	"owner": "cm9orztei00010cjs9wt2dg7x" 
	"speciality": "",
	"date": "02/06/2025",
	"time": "14:00",
}
``` 

**PUT`/appointment/:id`**
```json
{
	"date": "02/06/2025",
	"time": "14:00"
}
``` 
**DELETE `/appointment`**
```json
{
	"pet": "cm9os8cyk00000cl85wvl1nxv",
	"owner": "cm9orztei00010cjs9wt2dg7x",
	"date": "02/06/2025"
}
``` 
