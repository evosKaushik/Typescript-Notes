# 📝 Optional Parameters in Functions and Methods

There are multiple ways to handle optional parameters in JavaScript.

Some common approaches are:

- `||` operator
- `??` (Nullish Coalescing) operator
- ES6 default parameters

```ts
function greet(name = "Guest") {
  return `Hello, ${name}`;
}
```

---

## In TypeScript

TypeScript also provides multiple approaches, such as:

- Using `typeof` for conditional checks.
- Using the optional parameter (`?`).
- Passing an object instead of multiple raw arguments.

---

## Why Use an Object Instead of Raw Arguments?

When using function parameters, **optional parameters must come after required parameters**.

This is because function arguments are matched by **their position (order)**.

For example:

```ts
function example(a: string, b?: number) {}
```

If an optional parameter is placed before a required one, TypeScript will report an error.

Using an object gives you more control because properties are matched by **name** instead of position.

This makes the function easier to read and maintain.