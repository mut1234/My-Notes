# Class Syntax

```js
/*
  Class
*/

class User {
  constructor(name, email) {
    this.name = name;
    this.email = email;
  }
  sayHello() {
    return `Hello ${this.name}`;
  }
  showEmail() {
    return `Your Email Is ${this.email}`;
  }
}

let user1 = new User("Mustafa", "M@n.jo");
let user2 = new User("Ahmed");

console.log(user1);
console.log(user2);

console.log(typeof User); // Function
```

# Class Static Properties And Methods

**Any functionality not have relation to the object we make it static.**

**static is special for the class**

**non static is special for the object**

```js
/*
  Class
  Static Properties & Methods
*/

class User {
  // Static Properties
  static counter = 0;

  constructor(name, email, counter) {
    this.name = name;
    this.email = email;
    this.counter = counter; //here this refreance to counter of inctance (object)
    User.counter++; //here counter is counter of class
  }
  sayHello() {
    return `Hello ${this.name}`;
  }
  showEmail() {
    return `Your Email Is ${this.email}`;
  }

  // Static Methods //to reach the counter of the class you should write static 
  static countObjects = function () {
    return `${this.counter } Objects Created.`;
  };
}
let user1 = new User("Mustafa", "M@n.jo", 2);
let user2 = new User("Ahmed", "M@n.jo", 2);
let user3 = new User("Osama", "M@n.jo", 2);
let user4 = new User("Ali", "M@n.jo", 2);
// let user2 = User("Ahmed", "M@n.jo"); // TypeError: Class constructor User

console.log(typeof User); // Function
console.log(User === User.prototype.constructor); // True

console.log(User.countObjects());
```

**if we delete static world**

```js
/*
  Class
  Static Properties & Methods
*/

class User {
  // Static Properties
  static counter = 0;

  constructor(name, email, counter) {
    this.name = name;
    this.email = email;
    this.counter = counter; //here this refreance to counter of inctance (object)
    User.counter++; //here counter is counter of class
  }
  sayHello() {
    return `Hello ${this.name}`;
  }
  showEmail() {
    return `Your Email Is ${this.email}`;
  }
	//here will go to the counter of object (2)
   countObjects = function () {
    return `${this.counter } Objects Created.`;
  };
}
let user1 = new User("Mustafa", "M@n.jo", 2);
let user2 = new User("Ahmed", "M@n.jo", 2);
let user3 = new User("Osama", "M@n.jo", 2);
let user4 = new User("Ali", "M@n.jo", 2);
// let user2 = User("Ahmed", "M@n.jo"); // TypeError: Class constructor User

console.log(typeof User); // Function
console.log(User === User.prototype.constructor); // True

console.log(user1.countObjects());
```

