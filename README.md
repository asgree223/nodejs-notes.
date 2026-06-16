# Node.js Notes

My Learning Journey and Documentation of Node.js

## 1. What is Node.js?

Node.js is a JavaScript runtime environment that allows us to run JavaScript outside the browser.

### Why do we use Node.js?

* To build backend applications
* To create APIs
* To work with databases
* To build real-time applications

---

## 2. Initializing a Node.js Project

### Command

```bash
npm init -y
```

### What I Learned

* Creates a package.json file
* Stores project information and dependencies

---

## 3. Modules in Node.js

### What is a Module?

A module is a reusable piece of code.

### Built-in Modules

* fs (File System)
* path
* http

### Example

```js
const fs = require('fs');
```

### What I Learned

* How to import modules using require()
* How to use built-in modules

---

## 4. File System (fs)

### Reading a File

```js
const fs = require('fs');

const data = fs.readFileSync('data.txt', 'utf-8');
console.log(data);
```

### Writing a File

```js
fs.writeFileSync('data.txt', 'Hello World');
```

### Deleting a File

```js
fs.unlinkSync('data.txt');
```

### What I Learned

* Reading files
* Writing files
* Deleting files
* Managing local data

---

## 5. HTTP Module

### Creating a Server

```js
const http = require('http');

const server = http.createServer((req, res) => {
  res.end('Hello World');
});

server.listen(3000);
```

### What I Learned

* Creating a server
* Handling requests and responses

---

## 6. Express.js

### What is Express?

Express is a Node.js framework used to build APIs and web applications.

### Installation

```bash
npm install express
```

### Basic Server

```js
const express = require('express');

const app = express();

app.get('/', (req, res) => {
  res.send('Hello World');
});

app.listen(3000);
```

### What I Learned

* Creating APIs
* Routing
* Sending responses

---

## 7. Middleware

### What is Middleware?

Middleware is a function that runs between the request and response.

### Example

```js
app.use(express.json());
```

### What I Learned

* Processing request data
* Handling JSON data

---

## 8. Environment Variables

### dotenv

```bash
npm install dotenv
```

```js
require('dotenv').config();
```

### What I Learned

* Storing sensitive data securely
* Using .env files

---

## 9. MongoDB

### What is MongoDB?

MongoDB is a NoSQL database that stores data in documents.

### Key Concepts

* Database
* Collection
* Document

### Example Document

```json
{
  "name": "Asgaree",
  "email": "asgaree@example.com"
}
```

### What I Learned

* MongoDB basics
* Collections and documents
* CRUD operations

---

## 10. MongoDB with Node.js

### Connecting MongoDB

```js
const mongoose = require('mongoose');

mongoose.connect(process.env.MONGO_URI);
```

### What I Learned

* Connecting Node.js with MongoDB
* Using MongoDB in backend applications

---

## 11. Overall Learning Summary

So far, I have learned:

* Node.js Basics
* npm and package.json
* Modules
* File System (fs)
* HTTP Module
* Express.js
* Middleware
* dotenv
* MongoDB Basics
* MongoDB Integration with Node.js
* Mongoose
* Schemas
* Models
* Creating Documents

---

## 12. Mongoose

### What is Mongoose?

Mongoose is an ODM (Object Data Modeling) library for MongoDB and Node.js. It provides a simple way to model application data and interact with MongoDB.

### Installation

```bash
npm install mongoose
```

### Connecting to MongoDB

```js
const mongoose = require('mongoose');

mongoose.connect(process.env.MONGO_URI)
  .then(() => console.log('MongoDB Connected'))
  .catch((err) => console.log(err));
```

### Schema

A Schema defines the structure of documents in a MongoDB collection.

```js
const mongoose = require('mongoose');

const userSchema = new mongoose.Schema({
  name: String,
  email: String,
  age: Number
});
```

### Model

A Model is created from a Schema and is used to interact with the database.

```js
const User = mongoose.model('User', userSchema);
```

### Create a Document

```js
const user = new User({
  name: 'John',
  email: 'john@example.com',
  age: 25
});

user.save();
```

### What I Learned

* Installing Mongoose
* Connecting MongoDB with Node.js
* Creating Schemas
* Creating Models
* Inserting Documents into MongoDB
* Understanding ODM concepts
