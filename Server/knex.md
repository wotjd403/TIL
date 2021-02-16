## knex 란?

knex는 SQL query builder 라이브러리로 사용이 쉽고 직관적이기 때문에 업무에서 사용해도 무리가 없다.

[Knex.js - A SQL Query Builder for Javascript](https://knexjs.org)

### knex install

```jsx
npm install knex --save
```

DB 정보를 이용해 knex 객체를 생성

```jsx
const knex = require('knex')({
  client: 'mysql',
  connection: {
    host : HOST_ADDR,
    user : DB_USER,
    password : DB_PASSWORD,
    database : DB_NAME
  }
})
```

knex 객체를 이용해서 **CRUD** 쿼리를 생성

```jsx
knex.select('id', 'name', 'age').from('users')

knex('users').insert({ name:'James Kook', age: 20 })
knex('users').update({ age: 21 }).where('id', 2)
knex('users').del().where('id', 2)
```

스키마를 변경하거나 데이터베이스를 업그레이드하려고 할 때에는 knex migration 명령을 이용한다.

```jsx
knex migrate:make add-attractions-table
```