# API "Listagem e cadastro de usuários"

Este projeto segue os princípios da Arquitetura Limpa (Clean Architecture), utilizando as tecnologias NODE, TYPESCRIPT, EXPRESS, UUID, JEST, ESLINT,  PRETTIER e SWAGGER. Implementa funcionalidades como cadastro de usuários, listagem para administradores, autenticação, restrição de acesso e gerenciamento de permissões, aderindo aos princípios do SOLID e ao padrão de design Repository. Além disso, possui documentação da API para facilitar o uso e a manutenção do sistema.


![imagem da documentação da api com o swagger](https://github.com/iamfelipy/rockseat-nodejs-chapter-ii-desafio2/blob/main/nodejs-swagger-api-user-solid-clean-arcthectiure.png?raw=true)

## Tecnologias Utilizadas

- NODE
- TYPESCRIPT
- EXPRESS
- SWAGGER
- UUID
- JEST
- ESLINT
- PRETTIER

## Funcionalidades

- Cadastro de Novos Usuários: Permitir que novos usuários se cadastrem na aplicação, -  fornecendo informações como nome, e-mail e senha.
- Listagem de Usuários (Apenas Admin): Permitir que usuários administradores acessem uma lista de todos os usuários cadastrados na aplicação.
- Autenticação de Usuários: Garantir que apenas usuários autenticados possam acessar as funcionalidades de listagem de usuários, protegendo a segurança e a privacidade dos dados.
- Restrição de Acesso: Implementar uma lógica de controle de acesso para garantir que apenas usuários administradores possam visualizar a lista completa de usuários cadastrados.
- Gerenciamento de Permissões: Permitir que usuários administradores concedam ou revoguem permissões de administração para outros usuários, garantindo uma gestão eficiente e segura dos privilégios de acesso.

## Testes

#### Testes do modelo:

Deve ser capaz de criar um usuário com todas as propriedades
Testes do repositório:

- Deve ser capaz de criar novos usuários
- Deve ser capaz de listar todos os usuários
- Deve ser capaz de encontrar um usuário por ID
- Deve ser capaz de encontrar um usuário por endereço de e-mail
- Deve ser capaz de tornar um usuário administrador

#### Testes dos casos de uso:

- Deve ser capaz de criar novos usuários
- Não deve ser capaz de criar novos usuários quando o e-mail já estiver sendo usado
- Deve ser capaz de tornar um usuário administrador
- Não deve ser capaz de tornar um usuário não existente como administrador
- Deve ser capaz de obter o perfil do usuário por ID
- Não deve ser capaz de mostrar o perfil de um usuário que não existe
- Deve ser capaz de listar todos os usuários
- Não deve ser possível para um usuário não administrador obter a lista de todos os usuários
- Não deve ser possível para um usuário não existente obter a lista de todos os usuários

#### Testes das rotas:

- Deve ser capaz de criar novos usuários
- Não deve ser capaz de criar novos usuários quando o e-mail já estiver sendo usado
- Deve ser capaz de tornar um usuário administrador
- Não deve ser capaz de tornar um usuário não existente como administrador
- Deve ser capaz de obter o perfil do usuário por ID
- Não deve ser capaz de mostrar o perfil de um usuário que não existe
- Deve ser capaz de listar todos os usuários
- Não deve ser possível para um usuário não administrador obter a lista de todos os usuários
- Não deve ser possível para um usuário não existente obter a lista de todos os usuários

## Instalação e execução do projeto

Clone o projeto

```bash
  git clone https://github.com/iamfelipy/rockseat-ignite-nodejs-chapter-i-desafio-3
```

Entre no diretório do projeto

```bash
  cd  rockseat-ignite-nodejs-chapter-i-desafio-3
```

Instale as dependências

```bash
  npm install
```

Inicie o servidor

```bash
  npm run dev
```

## Documentação da API

#### Criação de um usuário

```
  POST /users
```

A rota deve receber name, e email dentro do corpo da requisição para que seja possível cadastrar um usuário.

| Parâmetro   | Tipo       | Descrição                           |
| :---------- | :--------- | :---------------------------------- |
| `name` | `string` | **Obrigatório**. O nome do usuário|
| `email` | `string` | **Obrigatório**. O email do usuário|


#### Atualizar um usuário para admin

```
  PATCH /users/:user_id/admin
```

A rota deve receber, nos parâmetros da rota, o id de um usuário e transformar esse usuário em admin.


| Parâmetro   | Tipo       | Descrição                           |
| :---------- | :--------- | :---------------------------------- |
| `user_id` | `string` | **Obrigatório**. O ID do item que você quer |

#### Buscar um usuário especifico

```
  GET /users/:user_id
```

A rota deve receber, nos parâmetros da rota, o id de um usuário e devolver as informações do usuário encontrado pelo corpo da resposta.

| Parâmetro   | Tipo       | Descrição                                   |
| :---------- | :--------- | :------------------------------------------ |
| `:user_id`      | `string` | **Obrigatório**. O ID do item que você quer |

#### Retorna todos os usuários

```
  GET /users
```

A rota deve receber, pelo header da requisição, uma propriedade user_id contendo o id do usuário e retornar uma lista com todos os usuários cadastrados. O id deverá ser usado para validar se o usuário que está solicitando a listagem é um admin. O retorno da lista deve ser feito apenas se o usuário for admin. 

| Parâmetro   | Tipo       | Descrição                           |
| :---------- | :--------- | :---------------------------------- |
| `user_id` | `string` | **Obrigatório**. A chave da sua API |

## Links

[Notion rocketseat descrição do desafio](https://efficient-sloth-d85.notion.site/Desafio-02-Documentando-com-Swagger-8ce869ea608743e292851bd951f3239f)
