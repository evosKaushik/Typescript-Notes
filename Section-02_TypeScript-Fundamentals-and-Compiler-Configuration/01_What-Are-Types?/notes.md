# 📘 What Are Types?

## 🔹 What Are Types?

Types in TypeScript are similar to the data types we already have in JavaScript.

### Primitive Types

* string
* number
* boolean
* null
* undefined
* symbol
* bigint

---

## ✍️ Type Annotation Syntax

We can explicitly define the type of a variable.

```ts
let username: string = "Kaushik";
```

This tells TypeScript that `username` must always contain a string value.

---

## 🎯 Why Define Types?

When working with:

* API responses
* Database data
* User input
* Complex objects

we can define types to catch errors during development instead of at runtime.

---

## 🧠 Type Inference

TypeScript is smart enough to automatically determine a type based on the assigned value.

```ts
let age = 15;
```

TypeScript automatically infers:

```ts
let age: number;
```

This process is called **Type Inference**.

---

## ⚠️ The `any` Type

The `any` type disables TypeScript's type checking.

```ts
let value: any = "hello";

value = 123;
value = true;
```

TypeScript will allow all of these assignments without errors.

Because of this, `any` should be avoided whenever possible.

---




### One-Line Summary

> Types tell TypeScript what kind of data a value can hold, helping catch mistakes before the code runs.
