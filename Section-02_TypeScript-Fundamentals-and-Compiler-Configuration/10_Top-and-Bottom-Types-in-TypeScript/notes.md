# 📚 TypeScript: Top Types and Bottom Types

---

# 🔝 Top Types

Top types can represent **any possible value**.

## 1️⃣ `any`

```ts
let value: any = 10;

value = "Hello";
value = true;
value = {};
```

✅ Accepts any value.

✅ Allows all operations.

```ts
let value: any = 10;

value.toFixed(2); // No error
value.toUpperCase(); // No error
```

❌ TypeScript stops checking safety.

---

## 2️⃣ `unknown`

```ts
let value: unknown = 10;

value = "Hello";
value = true;
```

✅ Accepts any value.

❌ Doesn't allow operations directly.

```ts
let value: unknown = 10;

value.toFixed(2); // Error ❌
```

TypeScript says:

> "I don't know what this value is yet."

You must check the type first.

```ts
if (typeof value === "number") {
  value.toFixed(2); // ✅ Safe
}
```

---

# 🤔 Why Use `unknown` Instead of `any`?

### `any`

```ts
let data: any = "hello";

data.toFixed(2); // No TypeScript error ❌
```

Runtime:

```txt
TypeError: data.toFixed is not a function
```

---

### `unknown`

```ts
let data: unknown = "hello";

data.toFixed(2); // TypeScript Error ✅
```

You must narrow the type first:

```ts
if (typeof data === "string") {
  console.log(data.toUpperCase());
}
```

### 💡 Rule

Use `unknown` when receiving data from:

* 🌐 APIs
* 📄 JSON files
* 👤 User input
* 📦 External libraries

Use `any` only when absolutely necessary.

---

# 🔻 Bottom Types

Bottom types represent values that can **never exist** or indicate **no useful value**.

---

## 1️⃣ `never`

`never` means:

> 🚫 This value can never happen.

```ts
let value: never;
```

You cannot assign anything:

```ts
value = 10;      // ❌
value = "hello"; // ❌
```

---

### Function Returning `never`

```ts
function throwError(): never {
  throw new Error("Something went wrong");
}
```

The function never finishes normally.

---

### Exhaustive Type Checking

```ts
type Shape = "circle" | "square";

function getArea(shape: Shape) {
  switch (shape) {
    case "circle":
      return 10;

    case "square":
      return 20;

    default:
      const x: never = shape;
      return x;
  }
}
```

✅ Helps catch bugs when new cases are added.

---

## 2️⃣ `void`

`void` means:

> 📭 This function doesn't return anything useful.

```ts
function sayHello(): void {
  console.log("Hello");
}
```

JavaScript actually returns:

```js
undefined
```

But TypeScript represents it as:

```ts
void
```

---

### Example

```ts
function logMessage(): void {
  console.log("Message");
}
```

Return value:

```js
undefined
```

Type:

```ts
void
```

---

# 🎯 Quick Summary

| Type      | Category        | Meaning                                     |
| --------- | --------------- | ------------------------------------------- |
| `any`     | 🔝 Top Type     | Anything allowed, no type safety            |
| `unknown` | 🔝 Top Type     | Anything allowed, but must check type first |
| `never`   | 🔻 Bottom Type  | No value can ever exist                     |
| `void`    | 📭 Special Type | Function returns nothing useful             |

---

# 🧠 Easy Memory Trick

### 🔝 Top Types

Think:

> "I can store EVERYTHING here."

```ts
any
unknown
```

---

### 🔻 Bottom Types

Think:

> "Nothing can live here."

```ts
never
```

---

### 📭 Void

Think:

> "The function did some work but didn't send anything back."

```ts
function print(): void {}
```

---

# 🚀 Real-World Usage

### Use `unknown` For

* API responses
* User input
* External data
* JSON parsing

```ts
const response: unknown = await fetchData();
```

---

### Use `never` For

* Exhaustive switch statements
* Functions that always throw errors
* Impossible states

```ts
function fail(message: string): never {
  throw new Error(message);
}
```

---

### Use `void` For

Functions that perform actions but don't return meaningful data.

```ts
function saveUser(): void {
  console.log("User saved");
}
```

---

# 🔥 Interview Question

### Is `void` a Bottom Type?

❌ No.

Many beginners think:

```ts
never === void
```

But that's wrong.

`never` is the true bottom type because it contains **no values**.

`void` is a special type mainly used for function return values and is associated with `undefined`.

```ts
let a: void = undefined; // ✅
let b: never = undefined; // ❌
```

Therefore:

```txt
Top Types:
any, unknown

Bottom Type:
never

Special Return Type:
void
```
