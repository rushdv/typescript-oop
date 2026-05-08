# Why `any` is Dangerous and Why `unknown` is Safer in TypeScript

## Introduction

When learning TypeScript, many beginners use `any` because it feels easy and flexible. But in real projects, using `any` too much can create problems. That’s why developers often call it a “type safety hole”.

On the other hand, `unknown` gives flexibility while still keeping the code safe. In this blog, I will explain the difference between `any` and `unknown` in a simple way.

---

## What is `any`?

The `any` type means TypeScript will stop checking the variable type.

```ts
let data: any = "Hello";

data = 100;
data = true;
```

Here, the variable can store anything. TypeScript will not show errors.

The problem is that this can create bugs very easily.

### Example

```ts
let value: any = 50;

console.log(value.toUpperCase());
```

This code looks fine to TypeScript, but it will crash when running because numbers do not have the `toUpperCase()` method.

That is why `any` is called a type safety hole.

---

## Why `unknown` is Better

The `unknown` type is much safer.

```ts
let value: unknown = "TypeScript";
```

Like `any`, it can store different types of values. But TypeScript will not allow unsafe operations directly.

### Example

```ts
let value: unknown = 50;

console.log(value.toUpperCase());
```

This time TypeScript shows an error. It forces us to check the type first.

---

## What is Type Narrowing?

Type narrowing means checking the type before using the value.

### Example

```ts
let value: unknown = "Hello";

if (typeof value === "string") {
  console.log(value.toUpperCase());
}
```

Inside the `if` block, TypeScript understands that `value` is a string.

This makes the code safer and reduces runtime errors.

---

## Benefits of Using `unknown`

### Better Safety

TypeScript protects the code from invalid operations.

### Cleaner Code

Developers become more careful while handling data.

### Fewer Bugs

Most runtime errors can be avoided early.

---

## Conclusion

Using `any` may look simple at first, but it removes the main advantage of TypeScript. That’s why it should be avoided when possible.

The `unknown` type is a smarter and safer choice because it forces developers to check types before using values. Combined with type narrowing, it helps write secure and reliable applications.