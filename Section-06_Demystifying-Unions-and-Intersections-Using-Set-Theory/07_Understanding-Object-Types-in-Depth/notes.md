# 📝 Understanding Object Types in Depth

## 📏 Which Set is Larger?

Remember:

> **A type with fewer conditions is a larger set.**  
> **A type with more conditions is a smaller set.**

```ts
type T2 = { length: number };
// Larger set

type T3 = { length: number; name: string };
// Smaller set
```

Why?

`T2` only says:

> "The value must have a `length` property."

`T3` says:

> "The value must have a `length` property AND a `name` property."

So:

```text
T3 ⊂ T2
```

In simple words:

```text
{ length: number }
        ↓
   Larger Set

{ length: number; name: string }
        ↓
   Smaller Set
```

---

## 🧩 Object Types are Structural

TypeScript uses **structural typing**.

This means TypeScript mainly cares about:

> **"Does this value have the required properties?"**

It does not require the value to come from a particular class or object type.

For example:

```ts
type T1 = {
  length: number;
};

const obj: T1 = "Hi";
```

This works because a `string` has a `length` property:

```ts
"Hi".length; // 2
```

So `"Hi"` satisfies:

```ts
{
  length: number;
}
```

The important idea is:

```text
Required structure
       ↓
{ length: number }

"Hi"
 ↓
has length
 ↓
✅ Fits the type
```

### ⚠️ Important

The type:

```ts
{ length: number }
```

does **not** mean:

> "This must be an object."

It means:

> "This value must have an accessible `length` property whose type is `number`."

---

## 📦 Empty Object Type `{}`

The `{}` type is a little different.

```ts
const a: {} = "Hello";
const b: {} = 10;
const c: {} = true;
const d: {} = [];
const e: {} = {};
```

These are allowed because `{}` means:

> **Any non-nullish value.**

So:

```text
{} 
↓
Everything except
❌ null
❌ undefined
```

---

## 🚫 Why `null` and `undefined` are Not in `{}`

```ts
const obj: {} = null;       // ❌
const obj1: {} = undefined; // ❌
```

The reason is that `null` and `undefined` do not have properties that can safely be accessed.

For example:

```ts
const value = null;

value.test;
```

At runtime, this causes an error because there is no value from which `.test` can be read.

Whereas a normal value such as a string exists:

```ts
const value = "Hello";

value.test;
```

JavaScript can evaluate the property access and get:

```ts
undefined
```

---

## 🛡️ Why TypeScript Does This

TypeScript tries to prevent operations that could cause a **runtime error**.

So TypeScript does not allow:

```ts
const obj: {} = null;
```

because later:

```ts
obj.test;
```

could crash the program.

Instead, TypeScript forces us to handle the possibility of `null` or `undefined`.

---

## 🧠 Set View

Think about it using sets:

```text
                    All JavaScript Values
                           │
          ┌────────────────┴────────────────┐
          │                                 │
      null / undefined                 Non-nullish
                                             │
                                             ↓
                                            {}
```

And for object structures:

```text
{ length: number }
        │
        └── contains values that have length

{ length: number; name: string }
        │
        └── contains fewer values
            because it has an extra condition
```

---

## 📌 Quick Summary

- 📏 Fewer conditions → **Larger set**
- 📏 More conditions → **Smaller set**
- 🧩 TypeScript uses **structural typing**
- 🔍 `{ length: number }` means the value must have a `length` property of type `number`
- 📦 `{}` means **any non-nullish value**
- 🚫 `{}` does not include `null` or `undefined`
- 🛡️ TypeScript prevents unsafe property access that could cause runtime errors