# Description

We have to create a function that receives a connection string with password included and you have to mask the password i.e. change password by asterisks.

Preconditions:

- non empty valid url
- password always next to string section password=
- assume password will not contain ampersand sign for sake of simplicity
- to make it more real it has non ASCII characters
- "password=" and "user" will occur only once

> _"empty passwords are not validated but best solutions take empty passwords into account"_

Example:

---

**input**

> _"jdbc:mysql://sdasdasdasd:szdasdasd:dfsdfsdfsdf/sdfsdfsdf?user=root&password=12345"_

**output**

> \*"jdbc:mysql://sdasdasdasd:szdasdasd:dfsdfsdfsdf/sdfsdfsdf?user=root&password=**\***"\*

**Extra readings:**

https://alvinalexander.com/java/jdbc-connection-string-mysql-postgresql-sqlserver

---

## Solution

```js
const hidePasswordFromConnection = (urlString) =>
  urlString.replace(/(?<=password=)([^&])*/, (c) => "*".repeat(c.length));
```
