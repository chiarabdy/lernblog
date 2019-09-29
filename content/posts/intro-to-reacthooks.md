+++
title = "Intro-to-reactHooks"
date = "2019-09-05"
draft = false
pinned = false
image = "/img/reactHooks.png"
+++

# Introducing Hooks
Hooks are a new addition in React 16.8. They let you use state and other React features without writing a class.

```javascript
import React, { useState } from 'react';

function Example() {
  // Declare a new state variable, which we'll call "count"
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>
        Click me
      </button>
    </div>
  );
}
```

This new function **useState** is the first “Hook”