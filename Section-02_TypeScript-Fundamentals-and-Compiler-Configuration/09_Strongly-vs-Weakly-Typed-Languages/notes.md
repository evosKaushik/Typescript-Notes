# 💪 Strongly vs Weakly Typed Languages

## 🔒 Strongly Typed Languages

Strongly typed languages enforce strict type rules and do **not automatically perform unsafe type conversions** during operations.

### Examples

* TypeScript
* Java
* C
* C++
* Go
* Rust

### Example

```ts
let age: number = 18;

age = "18"; // ❌ Error
```

---

## 🔓 Weakly Typed Languages

Weakly typed languages are more flexible with types and may **automatically convert data types** during operations instead of throwing an error.

### Examples

* JavaScript
* PHP

### Example

```js
console.log("5" + 5);
```

Output:

```text
55
```

JavaScript automatically converts `5` (number) into `"5"` (string) and concatenates them.

---

## ⚖️ Comparison

| Feature                   | 🔒 Strongly Typed | 🔓 Weakly Typed  |
| ------------------------- | ----------------- | ---------------- |
| Type Safety               | ✅ High            | ⚠️ Lower         |
| Automatic Type Conversion | ❌ Limited         | ✅ Common         |
| Runtime Bugs              | ✅ Fewer           | ⚠️ More Possible |
| Flexibility               | ❌ Less            | ✅ More           |
| Error Detection           | ✅ Earlier         | ⚠️ Often Later   |

> 📝 Note: A language can be both **statically typed** and **strongly typed** (e.g., TypeScript, Go, Rust), or **dynamically typed** and **strongly typed** (e.g., Python).
