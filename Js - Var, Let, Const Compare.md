# Var

- Redeclare (Yes)

```js
var a = 1;
var a = 1;

console.log(a);
```

- Access Before Declare (Undefined)

```js
console.log(a);
var a = 1;
```

- Variable Scope Drama (Added To Window)

```js
aabb = 1; //its will add to object scope window object
```

# Let

- Redeclare (No)

```js
var a = 1;
var a = 1;

console.log(a);//Error
```

- Access Before Declare (Error)

  ```js
  console.log(a);
  var a = 1;//Error
  ```

- Variable Scope Drama (Nothing happen)

# Const 

- Redeclare (Error)

```js
var a = 1;
var a = 1;

console.log(a);//Error
```

- Access Before Declare (Error)

  ```js
  console.log(a);
  var a = 1;//Error
  ```

- Variable Scope Drama (Nothing happen)



# Block or Function Scope for  Var,let,const

```js
function hi(){
    if(true){
        var a ='Javascript';
        let b ='c++';
        const c = 'Python';
        console.log(a);
        console.log(b);
        console.log(c);
    }
    	console.log("Outside If Statement");
        console.log(a);//just the var work
        console.log(b);
        console.log(c);
}
hi();
```

![img](https://miro.medium.com/max/700/1*6aIZJll5sYRkRuFNsX9jXw.jpeg)

you can declare variable type like this

```
let employeeName = "John";
// or 
let employeeName:string = "John";
```

