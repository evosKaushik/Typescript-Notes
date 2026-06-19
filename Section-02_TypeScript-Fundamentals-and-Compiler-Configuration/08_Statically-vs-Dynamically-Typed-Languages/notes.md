# 🆚 Statically vs Dynamically Typed Languages

## 🔵 Statically Typed Languages

✅ Type errors are checked **before the program runs**.

✅ Variables can contain only **one specific data type**.

### 📌 Examples

* 🐹 Go
* ⚙️ C
* ⚙️ C++
* 🔷 TypeScript
* ☕ Java

---

## 🟡 Dynamically Typed Languages

✅ Type errors are checked **at runtime**.

✅ Variables can hold **multiple data types**, which can increase the chances of bugs.

---

## 📊 Comparison

| Feature                     | 🔵 Static Typing | 🟡 Dynamic Typing |
| --------------------------- | ---------------- | ----------------- |
| ⏰ When verification happens | Before execution | During execution  |
| 🚨 Errors detected          | Early            | Late              |
| 📦 Variable type            | Fixed            | Can change        |
| 🛡️ Safety                  | Higher           | Lower             |

---

## 🧠 Type Inference

The data type of a variable is automatically inferred from the value stored in that variable.

### 📌 Example

```ts
let age = 15;
```

➡️ TypeScript automatically infers that `age` is a `number`.

---

## ⭐ Why Prefer Statically Typed Languages

* ✅ Errors are caught before the code executes.
* 📈 Great for large-scale applications.
* 👥 Great for team collaboration.
* 📖 Code feels like self-documentation.
