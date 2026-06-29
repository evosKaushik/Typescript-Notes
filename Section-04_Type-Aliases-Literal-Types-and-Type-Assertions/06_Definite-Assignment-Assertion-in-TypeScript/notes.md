# Definite Assignment Assertion in TypeScript

## What is it?

Definite Assignment Assertion tells **TypeScript**:

> **"Trust me, this variable will definitely be assigned a value before it is used."**

TypeScript stops checking whether the variable was initialized.

---

## Syntax

```ts
let username!: string;
```

The `!` is placed **after the variable name** and **before the type annotation**.

---

## Why is it used?

Normally, TypeScript gives an error if a variable is declared but not initialized.

```ts
let username: string;

console.log(username); // ❌ Error
```

Using Definite Assignment Assertion:

```ts
let username!: string;

username = "Kaushik";

console.log(username); // ✅ TypeScript is satisfied
```

Here, we are promising TypeScript that the variable **will be assigned before it is actually used**.

---

## Difference from Non-Null Assertion

| Non-Null Assertion | Definite Assignment Assertion |
|--------------------|-------------------------------|
| Used while accessing a value | Used while declaring a variable |
| Removes `null` and `undefined` from a value's type | Tells TypeScript that the variable will definitely be initialized later |
| Syntax: `value!` | Syntax: `let value!: string` |

---

## When should you use it?

Use it **only when you are absolutely sure** the variable will be initialized before it is accessed.

A common example is when a framework initializes the variable for you.

```ts
class User {
  name!: string;
}
```

---

## Why is it dangerous?

TypeScript trusts you completely.

If you forget to assign a value, your program may fail at runtime.

```ts
let username!: string;

console.log(username.toUpperCase()); // ❌ Runtime Error
```

TypeScript does not complain, but JavaScript crashes because `username` is actually `undefined`.

---

## Production Practice

In production code, avoid using Definite Assignment Assertion unless it is genuinely required (for example, when working with dependency injection or certain frameworks).

Instead, prefer:

- Initializing the variable immediately.
- Using constructor initialization.
- Using proper null checks.
- Designing your code so TypeScript can verify initialization automatically.

Using `!` to silence TypeScript errors is usually considered a code smell and should not be used as a shortcut.

---

## Key Points

- `!` tells TypeScript to trust that the variable will be assigned later.
- It is used **during variable declaration**.
- TypeScript skips definite assignment checking.
- It can cause runtime errors if your promise is wrong.
- Prefer proper initialization over using `!` whenever possible.