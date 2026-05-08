# How Generics Make TypeScript More Reusable and Flexible

## Introduction

Generics are one of the most useful features in TypeScript. They help developers write reusable code without losing type safety.

Instead of writing separate functions or classes for different data types, generics allow us to write one flexible piece of code that can work with many types.

---

## Why Generics are Needed

Without generics, developers often write similar code multiple times.

Example:

```ts
function getString(value: string): string {
  return value;
}

function getNumber(value: number): number {
  return value;
}
```

Both functions are doing the same job, but for different data types.

This creates unnecessary repetition.

---

## Using Generics

Generics solve this problem easily.

### Example

```ts
function identity<T>(value: T): T {
  return value;
}
```

Now the same function can work with any type.

```ts
identity<string>("Hello");
identity<number>(100);
identity<boolean>(true);
```

TypeScript automatically understands the correct type.

---

## Benefits of Generics

### Reusable Code

One function or class can work with many types.

### Type Safety

Even though the code is flexible, TypeScript still checks the types properly.

### Cleaner Code

Projects become smaller, cleaner, and easier to maintain.

---

## Generics with Arrays

Generics are also very useful with arrays.

### Example

```ts
function getFirstElement<T>(array: T[]): T {
  return array[0];
}
```

Usage:

```ts
getFirstElement<number>([1, 2, 3]);
getFirstElement<string>(["A", "B", "C"]);
```

The same function works for different array types.

---

## Generics in Interfaces

Generics can also be used with interfaces.

### Example

```ts
interface ApiResponse<T> {
  success: boolean;
  data: T;
}
```

Usage:

```ts
const response: ApiResponse<string> = {
  success: true,
  data: "Data Loaded",
};
```

This makes interfaces more flexible and reusable.

---

## Generics in Classes

Generics can also be used inside classes.

### Example

```ts
class DataStorage<T> {
  private items: T[] = [];

  addItem(item: T): void {
    this.items.push(item);
  }

  getItems(): T[] {
    return this.items;
  }
}
```

Usage:

```ts
const numberStorage = new DataStorage<number>();

numberStorage.addItem(10);
numberStorage.addItem(20);
```

This class can store any type of data safely.

---

## Conclusion

Generics make TypeScript applications more reusable, flexible, and type-safe. They help developers avoid duplicate code and create cleaner project structures.

For large projects, generics are very helpful because they save time and make code easier to manage.