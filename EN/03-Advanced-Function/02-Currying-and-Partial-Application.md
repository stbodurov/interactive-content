# Currying and Partial Application

[slide]
# Currying

We use **currying** to evaluate a function with **multiple arguments**, into a **sequence** of functions with **single argument**.

```js live
function sumOfThreeNums(a) {
  return (b) => {
    return (c) => {
      return a + b + c;
    };
  };
}
console.log(sumOfThreeNums(5)(6)(8));
```

Some example uses of **currying** include:

- **Template functions**

- **Code reuse**

- **Partial implementation**

- **Retaining scope**

[/slide]

[slide]
# Partial Application

**Reducing** the number of a function's **parameters** by converting it to a **new function with less parameters**, is called **Partial Application**.

Take a look at this example:

```js live 
function add(a, b) {
    return a + b;
}

function partial(func, a) {
     return (b) => func(a, b);
}

const newAdd = partial(add, 2);
console.log(newAdd(5));
```

The original `add()` function takes in two parameters.

The `partial()` function takes in a **function** and **an additional parameter**. 

After that, it **creates and returns a new function** that takes in **another argument**, and **appends** it to the first argument that was **already passed in**.

The resulting function takes in **one**, instead of **two** parameters.

[/slide]

[slide]
# Currying vs Partial Application

The main difference is as follows:

- **Currying** is turning a function with **multiple arguments** into a **chain of single-argument functions**.

- To **partially apply** means to pass to a function **fewer arguments than it has in its declaration**.

Currying is **not** the same as partial application.

It, however, **can be implemented** using partial application.

[/slide]
