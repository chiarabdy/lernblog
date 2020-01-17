+++
title = "Callbacks VS Promises"
date = "2020-01-17"
draft = false
pinned = false
image = "/img/callbacksVSpromises.jpg"
+++
## Promises
### Syntax
    new Promise(executor);

**Promises** are great when you do something that's going to take a long time in the background, such as downloading an image from a different server and you just wanna do something after it's complete, instead of making everything else waiting for it to be completed or you can **catch** it to see if it's failded so that  you can retriy it or give the user  an Err msg if it did fail
```js
const promise = new Promise((resolve, reject)=>{
    // Define the promise 
    let name = "chiar"
    if(name == "chiar"){
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
```
## Callbacks
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
                message: "LOL"
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
//Expecting: user typing / LOL
```
to avoid using callback inside callback inside callback which is wha's known as Callback hell we use promises, Here is converting the last example using callback into promises
```js
const userLeft = false
const userIsTyping = true

function promises(resolve, reject){
    if(userLeft){
        reject({
            name: "user Left",
            message: ":("
        })
    }else if(userIsTyping){
            reject({
                name: "user typing",
                message: "LOL"
            })
    }else{
        resolve("Thumbs up ")
    }
    }
    promises().then((message)=>{
        console.log("Success: " + message))
    }.catch (error)=>{
        console.log(error.name + " " + error.message)
    })
    //Expecting: user typing / LOL
```
