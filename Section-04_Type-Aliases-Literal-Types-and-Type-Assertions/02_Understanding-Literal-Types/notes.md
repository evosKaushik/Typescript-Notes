# 🎯 Understanding Literal Types

# 🤔 What are Literal Types?
A **Literal Type** is a type that allows **only one specific value**, instead of allowing every value of a general type like `string`, `number`, or `boolean`.

For example:

* `string` → Any string is allowed.
* `"hello"` → Only the exact string `"hello"` is allowed.

Think of it like this:

> **`string` = Any word** 📖
> **`"hello"` = Only one specific word** 🎯
---
# 📝 String Literal Type
You can define a variable that can hold only one specific string.

```ts
let greeting: "hello" = "hello";
```

✅ Valid

```ts
greeting = "hello";
```

❌ Error

```ts
greeting = "hi";
```

Because `"hi"` is not part of the allowed type.

---

# 📦 Literal Types with `const`

When you declare a variable using `const`, TypeScript automatically infers the most specific literal type.

```ts
const greeting = "hello";
```

TypeScript infers:

```ts
const greeting: "hello";
```

Instead of:

```ts
const greeting: string;
```

This happens because a `const` variable can never be reassigned, so TypeScript knows its value will always remain `"hello"`.

---

# 🔒 Using `as const`

Normally, a `let` variable is inferred as a general type because its value can change.

```ts
let greeting = "hello";
```

TypeScript infers:

```ts
let greeting: string;
```

If you want to preserve the literal type, use `as const`.

```ts
let greeting = "hello" as const;
```

Now the inferred type becomes:

```ts
let greeting: "hello";
```

⚠️ Since the variable has the literal type `"hello"`, assigning any other value will produce an error.

---

# 🌟 Literal Types with Numbers and Booleans

Literal types are not limited to strings.

## Number Literal

```ts
let version: 1 = 1;
```

---

## Boolean Literal

```ts
let isAdmin: true = true;
```

These variables can only hold their exact literal values.

---

# 🔗 Union of Literal Types

One of the most common uses of literal types is combining them with the **Union (`|`) operator**.

This allows a variable to accept **only a predefined set of values**.

```ts
type Direction =
  | "left"
  | "right"
  | "up"
  | "down";
```

Now only these four values are allowed.

```ts
let move: Direction;

move = "left";   // ✅
move = "right";  // ✅

move = "forward"; // ❌ Error
```

This is much safer than using a plain `string`, where any value would be accepted.

---

# 🧠 What happens behind the scenes?

Literal types exist **only in TypeScript**.

Example:

```ts
type Direction = "left" | "right";

let move: Direction = "left";
```

Compiles to:

```js
let move = "left";
```

Notice that all type information is removed because JavaScript does not understand literal types.

---

# 🚀 Production Perspective

Literal types are heavily used in large production applications to make APIs predictable and type-safe.

Common use cases include:

* 🎮 Game movement directions (`"left" | "right"`)
* 🌙 Theme selection (`"light" | "dark"`)
* 📦 Order status (`"pending" | "shipped" | "delivered"`)
* 🌐 HTTP methods (`"GET" | "POST" | "PUT" | "DELETE"`)
* ⚛️ React component variants (`"primary" | "secondary"`)

Using literal types helps catch invalid values during development instead of discovering bugs at runtime.

---

# 📚 Key Points

✅ A literal type represents one exact value.

✅ It can be a string, number, or boolean.

✅ `const` automatically infers literal types.

✅ `as const` preserves literal types for values that would otherwise be widened.

✅ Literal types become much more powerful when combined with union types.

✅ They exist only during TypeScript compilation and are removed in JavaScript.

---

# 🎯 Remember

> **`string` → Any string**
> **`"hello"` → Only the string `"hello"`**
> **`"left" | "right"` → Only the listed values are allowed**
