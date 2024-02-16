# Hello, SQLite

Preloaded libraries:

```js echo
SQLite
```

```js echo
SQLiteDatabaseClient
```

Load from a URL:

```js echo
const db = await SQLiteDatabaseClient.open("https://static.observableusercontent.com/files/b3711cfd9bdf50cbe4e74751164d28e907ce366cd4bf56a39a980a48fdc5f998c42a019716a8033e2b54defdd97e4a55ebe4f6464b4f0678ea0311532605a115");
display(db);
```

```js echo
Inputs.table(await db.sql`SELECT * FROM customers`)
```

Load from a local file:

```js echo
const localDb = await FileAttachment("chinook.db").sqlite();
display(localDb);
```

```js
Inputs.table(await localDb.sql`SELECT * FROM customers`)
```