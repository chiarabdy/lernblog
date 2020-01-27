+++
title = "MongoDB"
date = "2020-01-27"
draft = false
pinned = false
image = "/img/mongodb.jpg"
+++
## MongoDB
MongoDB is a database that stores data records (documents) for use by an application. 
Mongo is a non-relational, "NoSQL" database, it stores all associated data within one record, instead of storing it across many preset tables as in a SQL database.

## Mongoose
``Mongoose.js`` is an npm module for Node.js that allows you to write objects for Mongo as you would in JavaScript. This can make it easier to construct documents for storage in Mongo.
### MOngo Shell
- display the using database 
    db
- switch between databses
    user <database>
- switch to non-existing DB

```js
use myNewDatabase
db.myCollection.insertOne( { x: 1 } );
```
- show a list of db
    show dbs

- Create new DB
    user <name>
- show current DB
    db
- create a user
```js
db.createUser({
    user: '',
    pwd: '',
    roles:['readWrite', 'dbAdmin' ]
})
```
- Create a collection:

Collections are similar to tables in a relational DB, basically they just hold documents and records
```js
db.createCollection('randomName')
```
To see the collections
    show collections
- Add data into the collections
```js
db.randomName.insert({
    first_name: "",
    last_name: ""
})
```
To see the data in the collections
```js
db.randomName.find()
```
- Format Printed Results

```js
db.myCollection.find().pretty
```
- updating field

```js
db.myCollection.update({first_name: "John"}, {first_name: "john", last_name: "Doe", gender: "male"})
```
in update in order to update without repeating everything we use {$set}
```js
db.myCollection.update({first_name: "John"}, {{$set:{gender: "male"}})
```
- increment numeric values:
```js
db.myCollection.update({first_name: "John"}, {{$set:{age: 31}})
db.myCollection.update({first_name:"steven", {$inc:{age:5}}});
```

## Introduction to the MongoDB and Mongoose Challenges
* install and setup mongoDB and Mongoose
```js
npm install mongodb
npm install mongoose
// in server.js

```
* Create a model
    CRUD Part I - CREATE

**Schema:** Each schema ``maps`` to a ***MongoDB collection***. It defines the shape of the documents within that collection.
***Schemas*** are building block for Models. They can be nested to create complex models, but in this case we’ll keep things simple. A ***model*** allows you to create instances of your objects, called documents.

    Create a person having this prototype :
```sql
- Person Prototype -
--------------------
name : string [required]
age : number
favoriteFoods : array of strings (*)
```
* 