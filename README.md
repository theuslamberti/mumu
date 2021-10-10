# Plano de estudos

## Objetivo

Desenvolver uma base de conhecimento efetiva pra dar confiança em uma entrevista de emprego vaga júnior.

## Tecnologias a serem aprendidas e utilizadas

### 1ª parte (~ 2 meses)

- Git e Github (nada deve vir antes disso)
- NodeJS com Typescript
- Introdução aos métodos HTTP e o que eles significam (GET, POST, PUT, PATCH, DELETE), códigos de retorno e idempotência.
- Biblioteca ExpressJS para construção de API's no NodeJS
- Entender a diferença entre linguagem com tipagem estática vs tipagem dinâmica
- Uso de classes, objetos e interfaces
- Software para testar API's (usaremos o Insomnia)

### 2ª parte (~ 1 mês e meio)

- Banco de dados, queries simples em SQL e Postgres
- Containers, Docker e uso do banco de dados em container
- Migrar o código para uso com o banco de dados postgres
- Autenticação básica com uma API Key

### 3ª parte (~ ...)

- Aws?

## Execução

### 1ª parte

A intenção é que seja desenvolvido um software capaz de registrar dois tipos de entidades: pessoas e tarefas. Depois que a primeira parte do estudo estiver pronta, a intenção é que usemos esse software pra registrar as próximas tarefas do plano de estudos.

A entidade "Person" deve conter as seguintes informações:

- name
- email
- createdAt
- updatedAt

A entidade "Task" deve conter as seguinte informações:

- id
- email
- description
- estimate
- duration
- done
- createdAt
- updatedAt

Durante o desenvolvimento, devem ser usadas duas branches no git: main, e uma branch efêmera para desenvolvimento.

Para a entidade "Person" os seguintes métodos HTTP devem ser expostos através da API:

- GET /
  Deve retornar todos os usuários salvos na base.
- GET /:email
  Deve retornar todas as informações de um usuário específico, ou retornar um erro caso o usuário não exista.
- POST /
  Deve salvar um novo usuário na base. No corpo da requisição devem ser passados nome e email.

Para a entidade "Task" os seguintes métodos HTTP devem ser expostos através da API:

- GET /
  Deve retornar todas as tasks salvas na base.
- GET /:email
  Deve retornar todas as tasks sendo feitas pelo usuário com o email fornecido.  
  (os métodos acima devem ter a opção de um filtro chamado "done" com valor booleano, que irá fazer as queries acima de acordo com o filtro)
- POST /
  Deve criar uma nova task na base. No corpo da requisição devem ser passados descrição, estimativa e o email do usuário vinculado à tarefa. Caso o usuário passado não exista na base, um erro deve ser retornado e a task não deve ser salva.
- PATCH /:id/duration
  Deve alterar a duração da tarefa com o id fornecido (quanto tempo está levando para realizá-la). No corpo da requisição deve ser enviado um atributo de tempo que será somado à duração já existente na base.

Em ordem:

- Baixe o Gitkraken
- Verifique se já está instalado ou instale o git (provavelmente já estará instalado no Linux)
- Clone o repositório https://github.com/herzog0/mumu
- Crie uma branch chamada staging
- Procure "initialize typescript project" e siga algum passo a passo para criar um novo projeto em typescript. Provavelmente você terá que instalar o NodeJS na sua máquina. Quando for instalar ele, ignore a versão que o tutorial indicar e instale a versão 14.x.x mais recente (o importante é o 14 no início do número de versão, pra gente tanto faz os números que vêm depois).
