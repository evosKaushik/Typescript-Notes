# Interfaces in TypeScript

## What is an Interface?

An **interface** is used to define the **shape (structure)** of an object.

It tells TypeScript what properties an object should have and what their types should be.

---

## Syntax

```ts
interface User {
  name: string;
  age: number;
  isStudent: boolean;
}
```

Using the interface:

```ts
const user: User = {
  name: "xyz",
  age: 52,
  isStudent: true,
};
```

---

## Relation with `type`

An interface and a `type` can both describe the shape of an object.

Using `type`:

```ts
type User = {
  name: string;
  age: number;
  isStudent: boolean;
};
```

Using `interface`:

```ts
interface User {
  name: string;
  age: number;
  isStudent: boolean;
}
```

The syntax difference is:

- `type` uses `=`
- `interface` does **not** use `=`

---

## When should you use an Interface?

Interfaces are mainly used for defining object structures.

Examples:

- Objects
- Function parameters
- Class contracts
- API response models
- React component props

---

## Production Practice

In production code, many teams prefer **interfaces** for defining object shapes because they are easy to extend and are designed specifically for objects.

Use `type` when you need advanced TypeScript features like:

- Union types
- Intersection types
- Tuples
- Conditional types
- Mapped types

---

## Key Points

- An interface defines the structure of an object.
- It is similar to using an object `type`, but it is **not** a type alias.
- `interface` does not use `=`.
- Interfaces are primarily used for object shapes.
- Both `interface` and `type` disappear after TypeScript is compiled to JavaScript.