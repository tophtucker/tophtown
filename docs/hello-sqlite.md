# Hello, SQLite

```js echo
const db = await FileAttachment("chinook.db").sqlite();
const customers = await db.sql`SELECT * FROM customers`;
display(Inputs.table(customers));
```
