# Builder Design Pattern

### Introduction

* Builder Design Pattern, which is a pattern used to help construct complex objects. It helps separate object construction from its representation which will help us reuse this to create different representations
    
* It provides a flexible and step-by-step approach towards making these objects and keeps the representation, and the process of creation shielded
    

### Use Cases

* A good example would be that of a DOM, where you might need to create plenty of nodes and attributes. The construction process can get quite messy if you are building a complex DOM object. In cases like these, the builder pattern can be used
    

### Example

```typescript
/*
As you can see, there are many arguments that you need to pass while
creating an object, which can increase the complexity of the code base.
*/

class User {
  constructor(name, age, address, city, state, country) {
    this.name = name;
    this.age = age;
    this.address = address;
    this.city = city;
    this.state = state;
    this.country = country;
  }
}

const user = new User(
  "Kishan",
  undefined,
  undefined,
  "Ahmedabad",
  "Gujarat",
  "india"
);

console.log(user);

// solution using builderpattern
class UserBuilder {
  constructor(name) {
    this.name = name;
  }

  setAge(age) {
    this.age = age;
  }

  setAddress(address) {
    this.address = address;
  }

  setCity(city) {
    this.city = city;
  }

  setState(state) {
    this.state = state;
  }

  setCountry(country) {
    this.country = country;
  }
}

const newUser = new UserBuilder("naman");
newUser.setAge(20);
console.log(newUser);
```