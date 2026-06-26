# 📦 Tuples in TypeScript

> **Topic:** TypeScript (Static Type System)

---

# 🤔 What are Tuples?

A **Tuple** is a special type in **TypeScript** that allows you to define an array with a **fixed number of elements**, where **each position has its own specific data type**.

> ⚠️ **Important:** Tuples exist **only in the TypeScript type system**. They **do not exist at runtime** in JavaScript.

When TypeScript code is compiled, **all tuple information is removed**, leaving behind a normal JavaScript array.

```ts
// TypeScript
const user: [string, number] = ["Kaushik", 20];
```

⬇️ Compiles to:

```js
// JavaScript
const user = ["Kaushik", 20];
```

So, tuples are mainly used for:

* ✅ Better type safety
* ✅ Autocomplete
* ✅ Compile-time error checking
* ✅ Better developer experience

---

# 🎯 Why do we use Tuples?

Normally, an array can contain values in any order.

```ts
const arr = ["Kaushik", 20, true];
```

TypeScript only knows this is:

```ts
(string | number | boolean)[]
```

It **doesn't know** that:

* Index `0` should always be a string
* Index `1` should always be a number
* Index `2` should always be a boolean

A tuple lets you define this exact pattern.

---

# 📝 Tuple Syntax

```ts
const user: [string, number, boolean] = [
  "Kaushik",
  20,
  true,
];
```

Here:

| Index | Type    |
| ----- | ------- |
| 0     | string  |
| 1     | number  |
| 2     | boolean |

The order matters.

✅ Correct

```ts
["Kaushik", 20, true]
```

❌ Wrong

```ts
[20, "Kaushik", true]
```

---

# 🏷️ Named Tuples

You can make tuples more readable by naming each element.

```ts
const user: [
  name: string,
  age: number,
  isAdult: boolean
] = [
  "Kaushik",
  20,
  true,
];
```

These names are only for **documentation and editor hints**.

They do **not** exist in JavaScript.

---

# 📌 Accessing Tuple Values

Since each index has a known type, TypeScript provides accurate suggestions.

```ts
const user: [string, number, boolean] = [
  "Kaushik",
  20,
  true,
];

user[0]; // string
user[1]; // number
user[2]; // boolean
```

---

# ✏️ Updating Tuple Values

You can update values **using their index**, but the new value must match the expected type.

```ts
const user: [string, number] = ["Kaushik", 20];

user[0] = "Rahul"; // ✅
user[1] = 25;      // ✅

// ❌ Error
user[1] = "Twenty Five";
```

---

# ⚠️ Why are Tuples not completely consistent?

This is one of the strangest behaviors of tuples.

Although tuples have a fixed structure in TypeScript, **JavaScript arrays are still normal arrays at runtime**.

That means array methods like:

* `push()`
* `pop()`

still exist.

Example:

```ts
const user: [string, number] = ["Kaushik", 20];

user.push("Developer");
```

This is allowed in many cases because JavaScript arrays can always grow.

Now the array becomes:

```ts
["Kaushik", 20, "Developer"]
```

But TypeScript still thinks the tuple is:

```ts
[string, number]
```

When accessing by index:

```ts
user[2];
```

TypeScript often reports an error because index `2` is **not part of the tuple type**, even though the value exists at runtime.

Similarly,

```ts
user.pop();
```

removes the last element at runtime, but the tuple type itself doesn't dynamically change to reflect every runtime operation.

> 💡 This behavior exists because TypeScript's type system only checks code **at compile time**. It cannot change types based on every runtime array mutation.

---

# 🚀 Production Perspective

In large companies, tuples are typically used for:

* Returning multiple values from a function.
* Fixed coordinate values like `(x, y)`.
* RGB color values `(red, green, blue)`.
* Database query results with a fixed order.
* React hooks (for example, `useState()` returns a tuple).

For dynamic collections of data, developers usually prefer:

* Objects
* Interfaces
* Arrays

because they are easier to understand and maintain.

---

# 📚 Key Points

✅ Tuples exist only in TypeScript.

✅ After compilation, they become normal JavaScript arrays.

✅ Every position has a predefined type.

✅ Order is important.

✅ Named tuples improve readability.

✅ Values can be updated using their index if the type matches.

⚠️ Methods like `push()` and `pop()` still work because the runtime value is a normal JavaScript array, which can make tuple behavior seem inconsistent.

---

# 🎯 Remember

> **Tuple = Fixed pattern of values**
> **Array = Dynamic list of values**
