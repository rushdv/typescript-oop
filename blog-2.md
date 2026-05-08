# How Pick and Omit Help Reduce Code Duplication in TypeScript

## Introduction

While working on large projects, developers often need different versions of the same interface. Writing separate interfaces again and again makes the code messy and repetitive.

TypeScript provides two very useful utility types called `Pick` and `Omit`. These help developers reuse existing interfaces without repeating code.

---

## Understanding the Problem

Suppose we have a main interface for a user.

```ts
interface User {
  id: number;
  name: string;
  email: string;
  password: string;
}
```

Now imagine we want to create a public profile where the password should not be included.

Without utility types, we may create another interface manually.

```ts
interface PublicUser {
  id: number;
  name: string;
  email: string;
}
```

This works, but it repeats code.

---

## Using `Pick`

`Pick` allows us to select only the properties we need.

### Example

```ts
interface User {
  id: number;
  name: string;
  email: string;
  password: string;
}

type PublicUser = Pick<User, "id" | "name" | "email">;
```

Now TypeScript automatically creates a new type using selected properties.

This keeps the code shorter and cleaner.

---

## Using `Omit`

`Omit` does the opposite. It removes specific properties.

### Example

```ts
interface User {
  id: number;
  name: string;
  email: string;
  password: string;
}

type PublicUser = Omit<User, "password">;
```

Here, everything except `password` will remain.

---

## How They Keep Code DRY

DRY means “Don’t Repeat Yourself”.

Using `Pick` and `Omit` helps developers avoid rewriting the same properties many times.

### Benefits

- Less duplicate code
- Easier maintenance
- Cleaner structure
- Fewer mistakes

If the main interface changes later, the smaller types also update automatically.

---

## Real-Life Example

Suppose an online shop has a product interface.

```ts
interface Product {
  id: number;
  name: string;
  price: number;
  stock: number;
}
```

For customers, we may not want to show stock information.

```ts
type CustomerProduct = Omit<Product, "stock">;
```

This saves time and keeps the code organized.

---

## Conclusion

`Pick` and `Omit` are very useful utility types in TypeScript. They help developers create smaller and specialized versions of existing interfaces without repeating code.

By using these utility types, projects become cleaner, easier to maintain, and more professional.