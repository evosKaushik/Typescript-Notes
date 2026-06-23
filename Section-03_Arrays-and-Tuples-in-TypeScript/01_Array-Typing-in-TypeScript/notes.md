# 📚 Array Typing in TypeScript

## 🎯 How to Define an Array Type

```ts
const numbers: number[] = [1, 2, 3]
```

✅ This means:

* `numbers` is an array.
* Every value inside the array must be a `number`.

Examples:

```ts
const scores: number[] = [10, 20, 30]
```

❌ Error:

```ts
const scores: number[] = [10, "hello", 30]
```

Because `"hello"` is a string, not a number.

---

# 🔀 How to Define Multiple Data Types

```ts
const xyz: (string | number | boolean)[] = ["hi", 1, true]
```

✅ This means each element can be:

* `string`
* `number`
* `boolean`

Examples:

```ts
const data: (string | number | boolean)[] = [
  "Kaushik",
  15,
  true
]
```

You do **not** need to use all three types.

These are also valid:

```ts
const a: (string | number | boolean)[] = ["hello"]

const b: (string | number | boolean)[] = [1, 2, 3]

const c: (string | number | boolean)[] = [true, false]
```

✅ No error will occur because any of the allowed types can be used.

---

# 🚫 Empty Array in Global Context

```ts
const arr = []
```

TypeScript cannot determine what type of data will be stored inside the array.

Depending on the context and compiler settings, TypeScript may infer:

```ts
never[]
```

or

```ts
any[]
```

### What is `never[]`?

```ts
const arr: never[] = []
```

`never[]` means:

* This array can never contain any value.
* You cannot push anything into it.

Example:

```ts
const arr: never[] = []

arr.push(1) // ❌ Error
arr.push("hello") // ❌ Error
```

Because `never` means **no possible value**.

---

# 💡 Best Practice

Always provide a type when creating an empty array:

```ts
const numbers: number[] = []
```

or

```ts
const users: string[] = []
```

This makes TypeScript understand what kind of values will be stored later.

---

# 📝 Quick Revision

### Array of Numbers

```ts
const numbers: number[] = [1, 2, 3]
```

### Array of Multiple Types

```ts
const data: (string | number | boolean)[] = [
  "Hello",
  1,
  true
]
```

### Empty Typed Array

```ts
const users: string[] = []
```

### Never Array

```ts
const arr: never[] = []
```

* Cannot store any value.
* Used when TypeScript infers that no value should ever exist in the array.

---

## 🔥 Remember

> `number[]` → Array of numbers
> `(string | number)[]` → Array where each element can be string or number
> `never[]` → Array that can never contain any value
