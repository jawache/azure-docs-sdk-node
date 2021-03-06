---
title: Azure MySQL modules for Node.js
description: Reference for Azure MySQL modules for Node.js
keywords: Azure, Node, SDK, API, nodejs, javascript, database, MySQL
author: tomarcher
ms.author: tarcher
manager: douge
ms.date: 07/18/2017
ms.topic: article
ms.prod: azure
ms.technology: azure
ms.devlang: nodejs
ms.service: mysql
---

# Azure MySQL modules for Node.js

## Overview

The recommended client library for accessing Azure Database for MySQL is the open-source [Node.js connection library for Azure Database for MySQL](https://github.com/mysqljs/mysql). 

Learn more about [Azure Database for MySQL](https://docs.microsoft.com/azure/MySQL/)

## Client Package

### Install the npm module

Use npm to install the MySQL client module.

```bash
npm install mysql
```   

### Example

This example connects to a MySQL database and performs a simple query to retrieve all customers.

```javascript
const mysql = require('mysql');
const connection = mysql.createConnection({
  host: 'localhost',
  user: 'me',
  password: 'secret',
  database: 'my_db'
});

connection.connect();
const query = 'SELECT * FROM customers';
connection.query(query, (err, res) =>
  console.log(`We have ${res.length} customers`)
);

connection.end();
```

## Samples

[!INCLUDE [node-storage-samples](../docs-ref-conceptual/includes/mysql-samples.md)]

Explore more [sample Node.js code](https://azure.microsoft.com/resources/samples/?platform=nodejs) you can use in your apps.
