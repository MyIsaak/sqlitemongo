# sqlitemongo

![David](https://img.shields.io/david/myisaak/sqlitemongo)
![Snyk Vulnerabilities for npm package](https://img.shields.io/snyk/vulnerabilities/npm/sqlitemongo)
![npm](https://img.shields.io/npm/dw/sqlitemongo)

Migrate your sqlite3 database to mongodb.

## Why?

- Uses sqlite3 ids to avoid uploading duplicates
- Copy all tables into mongo collections in a single command

## What

It copies all tables from sqlite3 into mongo collections under a specified database. For example, if you have a sqlite3 database file `db.sqlite3` with tables: `table1` and `table2`, this tool uploads to a mongo database with collections `table1` and `table2`.

## CLI Usage

1. Install sqlitemongo globally using `sudo npm install --global sqlitemongo`.
2. Run `sqlitemongo <sqlitepath> <mongo uri> [<mongo database>]`
3. Done

## Module Usage

Just import sqlitemongo from npm `npm i sqlitemongo`, and start using as below:

```js
const sqlitemongo = require('sqlitemongo');

async function test() {
	var sqlitePath = './test.sqlite3';
	var mongoURI = 'mongo+srv://username:password@hostname.domain/test';
	var mongoDbName = 'test-database';
	await sqlitemongo(sqlitePath, mongoURI, mongoDbName /* optional */);
}
test().catch(console.error);
```
