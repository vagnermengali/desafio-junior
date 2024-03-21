##

<h1 align="center">
  User Crud
</h1>

<div align="center">
   <a href="#documentação-em-português">Leia em Português |</a>
  <a href="#documentation-in-english">Read in English</a>
</div>

---

# Documentação em português

<p align = "center">
Este é um crud de usuário que visa facilitar o acesso com funcionalidades básicas de um usuário e login.
</p>

<p align="center">
  <a href="#instalação">Instalação</a>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  <a href="#endpoints">Endpoints</a>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  <a href="#swagger">Swagger</a>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</p>

## **Instalação**

A seguir esta o passo-a-passo de instalação e execução em ambiente de desenvolvimento<br/>

A url base da api é http://localhost:3000

<p>1. Clone o repositório:</p>

```
git clone https://github.com/vagnermengali/user-crud
```

<p>2. Adentre na pasta raiz do projeto:</p>
  
```
cd user-crud
```
<p>3. Instale as dependências do projeto:</p>

```
yarn ou yarn install
```

<p>4. Crie seu schema:</p>

```
yarn prisma generate
```

<p>7. Aplique suas migrações:</p>
  
```
yarn prisma migrate dev
```
<p>8. Ative o server:</p>

```
yarn start:dev
```

<p align ='center'><a href="#--user-crud" >Voltar ao início</a></p>

---

## **Endpoints**

A API esta divida em /users sendo um CRUD e /login para geraão do token e melhor interação com a api. <br/>

<h2 align ='center'> Usuário </h2>

Nessa rotas o usuário pode acessar sem o token apenas POST/users, as demais usará o token para executar o CRUD de usuário :

##

`GET /users - FORMATO DA REQUISIÇÃO`

```
Não é necessário um corpo da requisição.

```

`GET /users - FORMATO DA RESPOSTA - STATUS 200`

```json
[
  {
    "username": "UserCrud UserCrud",
    "email": "user@gmail.com",
    "created_at": "2023-02-13T14:30:59.868Z",
    "updated_at": "2023-02-13T14:30:59.868Z"
  },
  {
    "username": "CrudUser CrudUser",
    "email": "crud@gmail.com",
    "created_at": "2023-02-13T13:08:00.947Z",
    "updated_at": "2023-02-13T14:33:49.762Z"
  }
]
```

##

`GET /users/profile - FORMATO DA REQUISIÇÃO`

```
Não é necessário um corpo da requisição.
```

`GET /users/profile - FORMATO DA RESPOSTA - STATUS 201`

```json
{
  "id": "fb6f2944-3ddc-4cef-a217-c0de75a1ee04",
  "username": "CrudUser CrudUser",
  "email": "crud@gmail.com",
  "created_at": "2023-02-13T13:08:00.947Z",
  "updated_at": "2023-02-13T14:31:49.390Z"
}
```

##

`POST /users - FORMATO DA REQUISIÇÃO`

```json
{
  "first_name": "UserCrud",
  "last_name": "UserCrud",
  "email": "user@gmail.com",
  "password": ".Crud123"
}
```

`POST /users- FORMATO DA RESPOSTA - STATUS 201`

```json
{
  "id": "6556e127-0518-4407-bd3e-65f5cdf1e869",
  "username": "UserCrud UserCrud",
  "email": "user@gmail.com",
  "password": "$2a$10$IrAEhGwMky/3ntH.aJA3ZuKgJnbpziUzcXTqlqyV33NGWJQH/EhEe",
  "created_at": "2023-02-13T14:30:59.868Z"
}
```

##

`PATCH /users/update - FORMATO DA REQUISIÇÃO`

Todos os campos são opcionais

```json
{
  "first_name": "CrudUser",
  "last_name": "CrudUser",
  "email": "crud@gmail.com",
  "password": ".User123"
}
```

`PATCH /users/update/ - FORMATO DA RESPOSTA - STATUS 200`

```json
{
  "id": "fb6f2944-3ddc-4cef-a217-c0de75a1ee04",
  "username": "CrudUser CrudUser",
  "email": "crud@gmail.com",
  "created_at": "2023-02-13T13:08:00.947Z",
  "updated_at": "2023-02-13T14:31:49.390Z"
}
```

##

`DELETE /users/delete/ - FORMATO DA REQUISIÇÃO`

```
Não é necessário um corpo da requisição.
```

`DELETE /users/delete/ - FORMATO DA RESPOSTA - STATUS 204`

```
Não a corpo de retorno.
```

##

<h2 align ='center'> Login </h2>

Nessa rota o usuário pode acessar sem o token para efetuar o login :

##

`POST /login - FORMATO DA REQUISIÇÃO`

```json
{
  "email": "user@gmail.com",
  "password": ".Crud123"
}
```

`POST /login - FORMATO DA RESPOSTA - STATUS 201`

```json
{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6InVzZXJAZ21haWwuY29tIiwiaWF0IjoxNjc2Mjk4NjQ2LCJleHAiOjE2NzYzODUwNDYsInN1YiI6IjdmY2M3MzY4LWZhZWEtNGIzZi1hYjhiLWRlODZjNTQ3ZTA5NyJ9.5IVEZ9popPzx3a7T0vPDI2ZlnnNISxBtPJREd7Zi2HE"
}
```

<p align ='center'><a href="#--user-crud" >Voltar ao início</a></p>

---

## **Swagger**

Api também conta a rota de interação, manipulação e documentação mais detalhada.

`api/`

<p align ='center'><a href="#--user-crud" >Voltar ao início</a></p>

---

# Documentation in English

<p align="center">
This is a user CRUD aiming to facilitate access with basic user and login functionalities.
</p>

<p align="center">
  <a href="#installation">Installation</a>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  <a href="#endpoints">Endpoints</a>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  <a href="#swagger">Swagger</a>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</p>

## **Installation**

Below is the step-by-step installation and execution guide in a development environment.

The base URL of the API is `http://localhost:3000`

<p>1. Clone the repository:</p>

```
git clone https://github.com/vagnermengali/user-crud
```

<p>2. Navigate to the project root directory:</p>
  
```
cd user-crud
```
<p>3. Install project dependencies:</p>

```
yarn ou yarn install
```

<p>4. Create your schema:</p>

```
yarn prisma generate
```

<p>7. Apply your migrations:</p>
  
```
yarn prisma migrate dev
```
<p>8. Start the server:</p>

```
yarn start:dev
```

<p align ='center'><a href="#--user-crud" >Back to Top</a></p>

---

## **Endpoints**

The API is divided into /users, which is a CRUD, and /login for token generation and better interaction with the API. <br/>

<h2 align ='center'> User </h2>

In these routes, the user can access without the token only POST/users, the others will use the token to execute the user CRUD :

##

`GET /users - REQUEST FORMAT`

```
No request body is required.

```

`GET /users - RESPONSE FORMAT - STATUS 200`

```json
[
  {
    "username": "UserCrud UserCrud",
    "email": "user@gmail.com",
    "created_at": "2023-02-13T14:30:59.868Z",
    "updated_at": "2023-02-13T14:30:59.868Z"
  },
  {
    "username": "CrudUser CrudUser",
    "email": "crud@gmail.com",
    "created_at": "2023-02-13T13:08:00.947Z",
    "updated_at": "2023-02-13T14:33:49.762Z"
  }
]
```

##

`GET /users/profile - REQUEST FORMAT`

```
No request body is required.
```

`GET /users/profile - RESPONSE FORMAT - STATUS 201`

```json
{
  "id": "fb6f2944-3ddc-4cef-a217-c0de75a1ee04",
  "username": "CrudUser CrudUser",
  "email": "crud@gmail.com",
  "created_at": "2023-02-13T13:08:00.947Z",
  "updated_at": "2023-02-13T14:31:49.390Z"
}
```

##

`POST /users - REQUEST FORMAT`

```json
{
  "first_name": "UserCrud",
  "last_name": "UserCrud",
  "email": "user@gmail.com",
  "password": ".Crud123"
}
```

`POST /users - RESPONSE FORMAT - STATUS 201`

```json
{
  "id": "6556e127-0518-4407-bd3e-65f5cdf1e869",
  "username": "UserCrud UserCrud",
  "email": "user@gmail.com",
  "password": "$2a$10$IrAEhGwMky/3ntH.aJA3ZuKgJnbpziUzcXTqlqyV33NGWJQH/EhEe",
  "created_at": "2023-02-13T14:30:59.868Z"
}
```

##

`PATCH /users/update - REQUEST FORMAT`

All fields are optional

```json
{
  "first_name": "CrudUser",
  "last_name": "CrudUser",
  "email": "crud@gmail.com",
  "password": ".User123"
}
```

`PATCH /users/update/ - RESPONSE FORMAT - STATUS 200`

```json
{
  "id": "fb6f2944-3ddc-4cef-a217-c0de75a1ee04",
  "username": "CrudUser CrudUser",
  "email": "crud@gmail.com",
  "created_at": "2023-02-13T13:08:00.947Z",
  "updated_at": "2023-02-13T14:31:49.390Z"
}
```

##

`DELETE /users/delete/ - REQUEST FORMAT`

```
No request body is required.
```

`DELETE /users/delete/ - RESPONSE FORMAT - STATUS 204`

```
No return body.
```

##

<h2 align ='center'> Login </h2>

In this route, the user can access without the token to perform the login :

##

`POST /login - REQUEST FORMAT`

```json
{
  "email": "user@gmail.com",
  "password": ".Crud123"
}
```

`POST /login - RESPONSE FORMAT - STATUS 201`

```json
{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6InVzZXJAZ21haWwuY29tIiwiaWF0IjoxNjc2Mjk4NjQ2LCJleHAiOjE2NzYzODUwNDYsInN1YiI6IjdmY2M3MzY4LWZhZWEtNGIzZi1hYjhiLWRlODZjNTQ3ZTA5NyJ9.5IVEZ9popPzx3a7T0vPDI2ZlnnNISxBtPJREd7Zi2HE"
}
```

<p align ='center'><a href="#--user-crud" >Back to Top</a></p>

---

## **Swagger**

API also includes routes for interaction, manipulation, and more detailed documentation.

`api/`

<p align ='center'><a href="#--user-crud" >Back to Top</a></p>

---
