# 📝 Types as Sets of JavaScript Values

## 💡 A Type is Just a Set

In TypeScript, every **type** is simply a **set of JavaScript values**.

- `number` → Set of all numbers
- `string` → Set of all strings
- `boolean` → Set of `true` and `false`
- `object` → Set of all objects
- `null` → Set containing only `null`
- `undefined` → Set containing only `undefined`

---

## 🌍 `unknown` = Universal Set

`unknown` is the **universal set** because **every JavaScript value belongs to it**.

```ts
const universalSet: unknown = "Hello";

const num: number = 10;
const str: string = "Hi";
const bool: boolean = true;
const un: undefined = undefined;
const nul: null = null;
const obj: object = {};

```

Everything above can be assigned to `unknown`.

---

## 🚫 `never` = Empty Set

`never` is the **empty set** because **no value belongs to it**.

```ts
let emptySet: never;
```

You cannot assign anything to a `never` variable.

---

## 📌 Quick Summary

- 🌍 `unknown` → Universal Set (contains every JavaScript value)
- 🚫 `never` → Empty Set (contains no values)
- 📝 Every other type is simply a set of specific JavaScript values.