# UserAuthenticator
## Resumo
Esta API de Autenticação foi desenvolvida para facilitar a gestão de usuários em aplicações que necessitam de registro, 
login e atualização de informações de usuários de forma segura. Utiliza o MongoDB como banco de dados para armazenar as informações dos usuários e 
JSON Web Tokens (JWT) para gerenciar sessões de usuários autenticados. 
O sistema é ideal para aplicações web e móveis que precisam de autenticação básica de usuários.

## 1. Instalação
### Requisitos

Node.js
MongoDB
Postman (opcional, para testar a API)

### Passos de Instalação

Clone o Repositório:

```
git clone https://github.com/brunobahri/userAuthenticator.git 
cd userAuthenticator

```
Instale as dependencias: 

```
npm install

```

Configurar MongoDB:

Certifique-se de que o MongoDB está instalado e funcionando em seu sistema. Você pode usar uma instância local do MongoDB ou uma instância hospedada (como o MongoDB Atlas).

## 2. Configuração

Arquivo .env
Configure o arquivo .env na raiz do projeto para definir variáveis de ambiente importantes

```
NODE_ENV=development
MONGO_URI=mongodb://localhost:27017/<SEU_DB_AQUI>
JWT_SECRET=CHAVE_SECRETA_AQUI

```
### Banco de Dados

Conexão com o Banco de Dados:

Utilize o arquivo config/database.js para gerenciar a conexão com o MongoDB.

### Segurança
JWT Secret:
Defina uma chave secreta forte para a assinatura de tokens JWT. Esta chave é usada para criar e verificar os tokens JWT.

## 3. Como Usar
### Endpoints da API

### Criação de Usuário (Cadastro)

POST /api/users/

Corpo da Requisição:

```
{
  "name": "Seu Nome",
  "email": "seuemail@example.com",
  "password": "suasenha"
}
```
### Resposta:

Sucesso: Retorna detalhes do usuário cadastrado.

### Login de Usuário

POST /api/users/login

Corpo da Requisição:
```
{
  "email": "seuemail@example.com",
  "password": "suasenha"
}
```
Resposta:

#### Sucesso: Retorna token de autenticação e detalhes do usuário.

### Atualização de Usuário

PUT /api/users/:id(retornada no sucesso da criação do usuário)
Cabeçalho: Authorization: Bearer TOKEN(retornado ao fazer login)
Corpo da Requisição:
```
{
  "name": "Nome Atualizado",
  "email": "emailatualizado@example.com"
}
```
Resposta:
Sucesso: Retorna detalhes do usuário atualizado.

Testando a API
Use o Postman ou qualquer outro cliente HTTP para testar os endpoints. Certifique-se de substituir TOKEN pelo token de autenticação JWT recebido após o login.

