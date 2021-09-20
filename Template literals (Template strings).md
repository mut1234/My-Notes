# Expression interpolation

In order to embed expressions within normal strings, you

```js
let a = 5;
let b = 10;
console.log('Fifteen is ' + (a + b) + ' and\nnot ' + (2 * a + b) + '.');
// "Fifteen is 15 and
// not 20."
```

```js
let a = 5;
let b = 10;
console.log(`Fifteen is ${a + b} and 
not ${2 * a + b}.`); //we use this rather concations
// "Fifteen is 15 and
// not 20."
```

# Nesting templates

In certain cases, nesting a template is the easiest (and perhaps more readable) way to have configurable strings. Within a back ticked template, it is simple to allow inner backticks by using them inside a placeholder `${ }` within the template.

**In ES5:**

```js
let classes = 'header';
classes += (isLargeScreen() ? '' : //if
            item.isCollapsed ? ' icon-expander' : //if else
            ' icon-collapser');//else
```

**In ES2015 with template literals and without nesting:**

```javascript
const classes = `header ${ isLargeScreen() ? '' : //if
  			 (item.isCollapsed ? 'icon-expander' : //if else
              'icon-collapser') }`; //else

```

**In ES2015 with nested template literals:**

```js
const classes = `header ${ isLargeScreen() ? '' ://if
  			`icon-${item.isCollapsed ? 'expander' ://if else
			'collapser'}` }`;//else
```

# Tagged templates

A more advanced form of template literals are *tagged* templates.

```js
let person = 'Mike';
let age = 28;

function myTag(strings, personExp, ageExp) {
  let str0 = strings[0]; // "That "
  let str1 = strings[1]; // " is a "
  let str2 = strings[2]; // "."

  let ageStr;
  if (ageExp > 99){
    ageStr = 'centenarian';
  } else {
    ageStr = 'youngster';
  }

  // We can even return a string built using a template literal
  return `${str0}${personExp}${str1}${ageStr}${str2}`;
}

let output = myTag`That ${ person } is a ${ age }.`;

console.log(output);
// That Mike is a youngster.
```

Tag functions don't even need to return a string!

```js
function template(strings, ...keys) {
  return (function(...values) {
    let dict = values[values.length - 1] || {};
    let result = [strings[0]];
    keys.forEach(function(key, i) {
      let value = Number.isInteger(key) ? values[key] : dict[key];
      result.push(value, strings[i + 1]);
    });
    return result.join('');
  });
}

let t1Closure = template`${0}${1}${0}!`;
//let t1Closure = template(["","","","!"],0,1,0);
t1Closure('Y', 'A');                      // "YAY!"

let t2Closure = template`${0} ${'foo'}!`;
//let t2Closure = template([""," ","!"],0,"foo");
t2Closure('Hello', {foo: 'World'}); // "Hello World!"

let t3Closure = template`I'm ${'name'}. I'm almost ${'age'} years old.`;
//let t3Closure = template(["I'm ", ". I'm almost ", " years old."], "name", "age");
t3Closure('foo', {name: 'MDN', age: 30}); //"I'm MDN. I'm almost 30 years old."
t3Closure({name: 'MDN', age: 30}); //"I'm MDN. I'm almost 30 years old."

```

# Raw strings

**String.raw()**

```js
let str = String.raw`Hi\n${2+3}!`;
// "Hi\\n5!"

str.length;
// 6

Array.from(str).join(',');
// "H,i,\\,n,5,!"
```

