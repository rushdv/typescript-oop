# How the Four Pillars of OOP Help in TypeScript Projects

## Introduction

Object-Oriented Programming, also known as OOP, is a programming style that helps developers organize code in a better and cleaner way.

There are four main pillars of OOP:

- Inheritance
- Polymorphism
- Abstraction
- Encapsulation

These concepts make large projects easier to manage and reduce code complexity.

---

## Inheritance

Inheritance allows one class to use properties and methods from another class.

### Example

```ts
class Person {
  constructor(public name: string) {}
}

class Student extends Person {
  constructor(name: string, public grade: string) {
    super(name);
  }
}
```

Here, the `Student` class inherits from the `Person` class.

This helps reduce duplicate code because common properties can stay in one parent class.

---

## Polymorphism

Polymorphism means the same method can behave differently in different classes.

### Example

```ts
class Animal {
  sound(): string {
    return "Animal Sound";
  }
}

class Cat extends Animal {
  sound(): string {
    return "Meow";
  }
}
```

Both classes use the same method name, but they return different outputs.

This makes the code more flexible.

---

## Abstraction

Abstraction hides unnecessary details and shows only important functionality.

### Example

```ts
abstract class Vehicle {
  abstract start(): void;
}

class Car extends Vehicle {
  start(): void {
    console.log("Car Started");
  }
}
```

Here, users only know that the vehicle can start. Internal details stay hidden.

This reduces complexity in large applications.

---

## Encapsulation

Encapsulation protects data from direct access.

### Example

```ts
class BankAccount {
  private balance: number = 1000;

  getBalance(): number {
    return this.balance;
  }
}
```

Here, the `balance` cannot be changed directly from outside the class.

This improves security and keeps the data controlled.

---

## Why OOP is Useful

OOP helps developers:

- Organize code properly
- Reduce duplication
- Make projects easier to maintain
- Build scalable applications

It is very useful when many developers work together on the same project.

---

## Conclusion

The four pillars of OOP help developers write cleaner and more manageable code. Inheritance reduces repetition, polymorphism increases flexibility, abstraction hides complexity, and encapsulation protects data.

Because of these advantages, OOP is widely used in modern TypeScript projects.