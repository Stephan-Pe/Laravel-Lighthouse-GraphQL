# Laravel GrapQL-Server

Based on an Article by [Christopher Moore](https://www.toptal.com/resume/christopher-moore)

Requires:

```
$ composer require nuwave/lighthouse

```
Which you have to publish

```
$ php artisan vendor:publish --provider="Nuwave\Lighthouse\LighthouseServiceProvider" --tag=config

```

And you have to create your GraphQL Schema 

```
$ mkdir graphql
$ touch ./graphql/schema.graphql

```

to play around you have to install [Graphql-Playground](https://github.com/graphql/graphql-playground) which you will find on [Github](https://github.com/graphql/graphql-playground)

in this [Christophers](https://www.toptal.com/graphql/laravel-graphql-server-tutorial) demo project an SQLite database is used. If you want to control whats going on in your db you can use [SQLiteStudio](https://sqlitestudio.pl/) which is a great tool working with SQLite databases.

Here some examples for queries and mutations:

```graphql
# Write your query or mutation here
{
  users(first:4) {
    paginatorInfo {
      total
      hasMorePages
    }
    data {
      id
      name
      email
    }
  }
}
```

```graphql
mutation {
  createUser(
    name:"John Doe"
    email:"john.doe@example.com"
    password: "secret"
  ) {
    id
    name
    email
  }
}
```
```graphql
mutation {
  login(email:"graphql@test.com", password:"secret")
}
```

```graphql
{
  articles(first:2) {
    paginatorInfo {
      total
      hasMorePages
    }
    data {
      id
      title
      author {
        name
        email
      }
    }
  }
}
```

