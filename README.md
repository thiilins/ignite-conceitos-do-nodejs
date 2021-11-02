<div align="center" id="top"> 
  <img src="./.github/banner-nodeJS.png" alt="Desafio" />

&#xa0;

  <!-- <a href="https://desafio.netlify.com">Demo</a> -->
</div>

<h1 align="center">Ignite | Trilha NodeJS: Conceitos do NodeJS</h1>

<p align="center">
  <img alt="Principal linguagem do projeto" src="https://img.shields.io/github/languages/top/thiilins/ignite-conceitos-do-nodejs?color=04d361&style=for-the-badge">

  <img alt="Quantidade de linguagens utilizadas" src="https://img.shields.io/github/languages/count/thiilins/ignite-conceitos-do-nodejs?color=04d361&style=for-the-badge">

  <img alt="Tamanho do repositório" src="https://img.shields.io/github/repo-size/thiilins/ignite-conceitos-do-nodejs?color=04d361&style=for-the-badge">

  <img alt="Licença" src="https://img.shields.io/github/license/thiilins/ignite-conceitos-do-nodejs?color=04d361&style=for-the-badge">

  <!-- <img alt="Github issues" src="https://img.shields.io/github/issues/thiilins/ignite-conceitos-do-nodejs?color=56BEB8" /> -->

  <!-- <img alt="Github forks" src="https://img.shields.io/github/forks/thiilins/ignite-conceitos-do-nodejs?color=56BEB8" /> -->

  <!-- <img alt="Github stars" src="https://img.shields.io/github/stars/thiilins/ignite-conceitos-do-nodejs?color=56BEB8" /> -->
</p>

<!-- Status -->

<!-- <h4 align="center">
	🚧  Desafio 🚀 Em construção...  🚧
</h4>

<hr> -->

<p align="center">
  <a href="#laptop-sobre-o-desafio">Sobre o desafio</a> &#xa0; |  &#xa0;
  <a href="#rocket-tecnologias">Tecnologias</a> &#xa0; | &#xa0;
  <a href="#white_check_mark-pré-requisitos">Pré requisitos</a> &#xa0; | &#xa0;
  <a href="#checkered_flag-começando">Começando</a> &#xa0; | &#xa0;
  <a href="#memo-licença">Licença</a> &#xa0; | &#xa0;
  <a href="https://github.com/thiilins" target="_blank">Autor</a>
</p>
<br>

# :computer: Sobre o desafio

Nesse desafio, você deverá criar uma aplicação para treinar o que aprendeu até agora no Node.js!
Essa será uma aplicação para gerenciar tarefas (em inglês _todos_).Será permitida a criação de um usuário com `name` e `username`, bem como fazer o CRUD de *todos*

- [x] Criar um novo _todo_;
- [x] Listar todos os _todos_;
- [x] Alterar o `title` e `deadline` de um _todo_ existente;
- [x] Marcar um _todo_ como feito;
- [x] Excluir um _todo_;

Tudo isso para cada usuário em específico (o `username` será passado pelo header). A seguir veremos com mais detalhes o que e como precisa ser feito 🚀

### POST `/users`

A rota deve receber `name`, e `username` dentro do corpo da requisição. Ao cadastrar um novo usuário, ele deve ser armazenado dentro de um objeto no seguinte formato:

```jsx
{
	id: 'uuid', // precisa ser um uuid
	name: 'Danilo Vieira',
	username: 'danilo',
	todos: []
}
```

Certifique-se que o ID seja um UUID, e de sempre iniciar a lista `todos` como um array vazio.
O objeto do usuário deve ser retornado na resposta da requisição.

### GET `/todos`

A rota deve receber, pelo header da requisição, uma propriedade `username` contendo o username do usuário e retornar uma lista com todas as tarefas desse usuário.

### POST `/todos`

A rota deve receber `title` e `deadline` dentro do corpo da requisição e, uma propriedade `username` contendo o username do usuário dentro do header da requisição. Ao criar um novo _todo_, ele deve ser armazenada dentro da lista `todos` do usuário que está criando essa tarefa. Cada tarefa deverá estar no seguinte formato: . Certifique-se que o ID seja um UUID.

```jsx
{
	id: 'uuid', // precisa ser um uuid
	title: 'Nome da tarefa',
	done: false,
	deadline: '2021-02-27T00:00:00.000Z',
	created_at: '2021-02-22T00:00:00.000Z'
}
```

**Observação**: Lembre-se de iniciar a propriedade `done` sempre como `false` ao criar um _todo_.

**Dica**: Ao fazer a requisição com o Insomnia ou Postman, preencha a data de `deadline` com o formato `ANO-MÊS-DIA` e ao salvar a tarefa pela rota, faça da seguinte forma:

```jsx
{
	id: 'uuid', // precisa ser um uuid
	title: 'Nome da tarefa',
	done: false,
	deadline: new Date(deadline),
	created_at: new Date()
}
```

Usar `new Date(deadline)` irá realizar a transformação da string "ANO-MÊS-DIA" (por exemplo "2021-02-25") para uma data válida do JavaScript.
O objeto do `todo` deve ser retornado na resposta da requisição.

### PUT `/todos/:id`

A rota deve receber, pelo header da requisição, uma propriedade `username` contendo o username do usuário e receber as propriedades `title` e `deadline` dentro do corpo. É preciso alterar **apenas** o `title` e o `deadline` da tarefa que possua o `id` igual ao `id` presente nos parâmetros da rota.

### PATCH `/todos/:id/done`

A rota deve receber, pelo header da requisição, uma propriedade `username` contendo o username do usuário e alterar a propriedade `done` para `true` no _todo_ que possuir um `id` igual ao `id` presente nos parâmetros da rota.

### DELETE `/todos/:id`

A rota deve receber, pelo header da requisição, uma propriedade `username` contendo o username do usuário e excluir o _todo_ que possuir um `id` igual ao `id` presente nos parâmetros da rota.

## :rocket: Tecnologias

As seguintes ferramentas foram usadas na construção do projeto:

- [Node.js](https://nodejs.org/en/)

## :white_check_mark: Pré requisitos

Antes de começar :checkered_flag:, você precisa ter o [Git](https://git-scm.com) e o [Node](https://nodejs.org/en/) instalados em sua maquina.

## :checkered_flag: Começando

```bash
# Clone este repositório
$ git clone https://github.com/thiilins/ignite-conceitos-do-nodejs

# Entre na pasta
$ cd desafio

# Instale as dependências
$ yarn

# Para iniciar o projeto
$ yarn start

# O app vai inicializar em <http://localhost:3000>
```

## :memo: Licença

Este projeto está sob licença MIT. Veja o arquivo [LICENSE](LICENSE.md) para mais detalhes.

Feito com :heart: por <a href="https://github.com/thiilins" target="_blank">Thiago Lins</a>

&#xa0;

<p align="right">(<a href="#top">Voltar para o topo</a>)</p>
