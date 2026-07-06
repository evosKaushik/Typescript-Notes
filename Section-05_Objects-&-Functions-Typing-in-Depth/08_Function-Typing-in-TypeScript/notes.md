# 📝 Function Typing in TypeScript

## Syntax

```ts
function add(a: string, b: string): string {
  return a + b;
}
```

### Parameter Types

```ts
(a: string, b: string)
```

Defines the types of arguments that the function accepts.

### Return Type

```ts
(): string
```

Specifies the return type of the function.

If you do not explicitly specify the return type, TypeScript **infers** it from the returned value.

---

## `void`

Sometimes a function does not return any value.

In that case, we use:

```ts
: void
```

In JavaScript, a function that does not return anything implicitly returns `undefined`.

### `void` Keyword in JavaScript

`void` is also a JavaScript keyword.

It evaluates an expression and always returns `undefined`.

---

## `never`

The `never` type is used when a function **never completes normally**.

Common examples include:

- Throwing an error.
- Running an infinite loop.

```ts
function throwError(): never {
  throw new Error("Something went wrong");
}
```

```ts
function infiniteLoop(): never {
  while (true) {}
}
```