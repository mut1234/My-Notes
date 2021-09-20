# Regular Function

```js
function print(){
    return 10;
};
console.log(print());

//or you can assign function like this
let print = function () {
    return 10;
};
console.log(print());
```

# Arrow Function

this only if you have one line only.

```js
let print = () => 10;
console.log(print());
```

if we don't have parameter we can use this

```js
let print = _ => 10; // like language in go
console.log(print());
```

another example here you can delete the () of parameter (only when we have one parameter)

```js
let print = num => num;
console.log(print(100));
```

if we have more than one parameter(here we can't remove () because we have more than two parameter)

```js
let print = (num1, num2) => num1 + num2;
console.log(print(100, 50));
```

