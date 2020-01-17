+++
title = "Callbacks - Promises - async/await"
date = "2020-01-17"
draft = false
pinned = false
image = "/img/callbacksVSpromises.jpg"
+++

# CALLBACKS
A `callback function` is a function which is accessible by another function, and is invoked after the first function if that first function completes
Callbacks is what promises are meant to replace

```js
const userLeft = false
const userIsTyping = true

function callbacks(callback, errorcallback){
    if(userLeft){
        errorcallback({
            name: "user Left",
            message: ":("
        })
    }else if(userIsTyping){
            errorcallback({
                name: "user typing",
                message: "I am Typing"
            })
    }else{
        callback("Thumbs up ")
    }
    }
    callbacks((message)=>{
        console.log("Success: " + message)
    }, (error)=>{
        console.log(error.name + " " + error.message)
    })
//Expecting: user typing / I am Typing
```

to avoid using **callback** inside **callback** inside **callback** which is what's known as Callback hell we use **PROMISES**

# PROMISES

### SYNTAX
    new Promise(executor);

**Promises** are great when you do something that's going to take a long time in the background, such as downloading an image from a different server and you just wanna do something after it's complete, instead of making everything else waiting for it to be completed or you can **catch** it to see if it's failded so that  you can retriy it or give the user  an Err msg if it did fail

First Let's Use the previous **callback** example and use **Promises** instead
 
```js
const userLeft = false
const userIsTyping = true

function promises(resolve, reject){
    if(userLeft){
        reject({
            name: "User",
            message: "The User Has Left"
        })
    }else if(userIsTyping){
            reject({
                name: "User",
                message: " The User is Typing"
            })
    }else{
        resolve("User has Logged in")
    }
    }
    promises().then((message)=>{
        console.log("Success: " + message))
    }.catch (error)=>{
        console.log(error.name + " " + error.message)
    })
    //Expecting: User/ The User is Typing
```

<!-- ```js
const promise = new Promise((resolve, reject)=>{
    // Define the promise 
    let name = "User"
    if(name === "User"){
        resolve("success")
    }else{
        reject("failed")
    }
})
    // Interact with Promises
promise.then((print) =>{
    console.log("Res " + print)
}).catch((print)=>{
    console.log("Rej" + print)
})
``` -->

## Promise.all()
The `Promise.all()` method **returns** a single **Promise** that fulfills when all of the promises passed as an iterable have been fulfilled or when the iterable contains no promises. It **rejects** with the reason of the first promise that rejects.
```js
const v1 = new Promise((res, rej)=>{
    res("Hey, this is V1")
})
const v2 = new Promise((res, rej)=>{
    res("Hey, this is V2")
})
const v3 = new Promise((res, rej)=>{
    res("Hey, this is V3")
})
Promise.all(
    [
        v1,
        v2,
        v3
    ]
).then((message)=>{
    console.log(message)

    //Expected to print 
    /* ["Hey, this is V1",
     * "Hey, this is V2",
    /* "Hey, this is V3"]
})
```
`Promise.all` run every single one of these promises and as soon as it done, it is then going to call **.then()** and **.catch()** depending on if they resolved or failed 

**.then()** will send an array of all of the successful messages, so it will send an array of all of these different resolved parameters.

## promise.race()
it returns as soon as the first promise is completed instead of waiting for everything to complete. This mean it will return a single promise
```js
Promise.race(
    [
        v1,
        v2,
        v3
    ]
).then((message)=>{
    console.log(message)

    //Expected to print 
    /* Hey, this is V1
})
```