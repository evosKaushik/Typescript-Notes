# 📝 Creating Reusable Function Types

Reusable function types can be created using either **`interface`** or **`type`**.

> **Good practice:** Prefer `type` for function types. Interfaces are generally used for object shapes and classes.

---

## Using `interface`

```ts
interface CommonFnType {
  (a: string, b: boolean): boolean;
}
```

---

## Using `type`

```ts
type CommonFnType = (a: string, b: boolean) => boolean;
```

---

## Using the Reusable Function Type

When using a reusable function type, define the function as a **function expression**.

```ts
const fn: CommonFnType = function (a, b) {
  return true;
};
```