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

## Mongo Shell

#### display the using database
    db

#### switch between databses
    user <database>

#### switch to non-existing DB
  use myNewDatabase
  db.myCollection.insertOne( { x: 1 } );

#### show a list of db
    show dbs

#### Create new DB
    user <name>

#### show current DB
    db

#### create a user
    db.createUser({
        user: '',
        pwd: '',
        roles:['readWrite', 'dbAdmin' ]
    })

#### Create a collection:

Collections are similar to tables in a relational DB, basically they just hold documents and records

    db.createCollection('randomName')

#### see the collections
    show collections

#### Add data into the collections

    db.randomName.insert({
        first_name: "",
        last_name: ""
    })

#### see the data in the collections

    db.randomName.find()


#### Format Printed Results

    db.myCollection.find().pretty

#### updating field

    db.myCollection.update({first_name: "John"}, {first_name: "john", last_name: "Doe", gender: "male"})


#### in update in order to update without repeating everything we use {$set}

    db.myCollection.update({first_name: "John"}, {{$set:{gender: "male"}})


#### increment numeric values:

    db.myCollection.update({first_name: "John"}, {{$set:{age: 31}})
    db.myCollection.update({first_name:"steven", {$inc:{age:5}}});

## Freecodecamp - MongoDB and Mongoose Challenges: 
1. Introduction to the MongoDB and Mongoose Challenges

* install and setup mongoDB and Mongoose

```js
// require the module and connect to the DB
const mongoose = require('mongoose');
mongoose.connect(process.env.MONGO_URI);

```
2. Create a model
    CRUD Part I - CREATE

**Schema:** Each schema ``maps`` to a ***MongoDB collection***. It defines the shape of the documents within that collection.
***Schemas*** are building block for Models. They can be nested to create complex models, but in this case we’ll keep things simple. A ***model*** allows you to create instances of your objects, called documents.

    Create a person having this prototype :

```js
// Create Schema
var Schema = mongoose.Schema;

const personSchema = new Schema({
  name: String,
  age: Number,
  favoriteFoods: [String]
});
// Modify the model
var Person = mongoose.model('Person', personSchema);
```

3. Create and Save a Record of a Model
* create and save a record of a **Person** model.
* Create a document instance using the **Person** constructor . 
* Pass to the constructor an object having the fields `name`, `age`,and `favoriteFoods`. Their types must be conformant to the ones in the Person `Schema`.
* call the method `document.save()` on the returned
document instance, passing to it a callback using the Node convention.
This is a common pattern, all the **CRUD** methods take a callback function like this as the last argument.

```js
var createAndSavePerson = done => {
  const person = new Person({
    name: 'Person',
    age: 18,
    favortieFoods: ['Hotdog', 'Beer']
  });
  person.save((err, data) => err ? done(err) : done(null, data));
};
```
4. Create Many Records with ``model.create()``
``Model.create()`` takes an array of objects like ``[{name: 'John', ...}, {...}, ...]`` as the first argument, and saves them all in the db.

```js
var createManyPeople = (arrayOfPeople, done) => {
  Person.create(arrayOfPeople, (err, data) => err ? done(err) : done(null, data));
};
```

5. Use model.find() to Search Your Database
