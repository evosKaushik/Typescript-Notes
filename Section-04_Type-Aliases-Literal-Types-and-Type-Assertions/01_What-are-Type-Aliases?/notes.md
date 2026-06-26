# 🏷️ Type Aliases in TypeScript

> **Topic:** TypeScript (Type System)

---

# 🤔 What are Type Aliases?

A **Type Alias** is a way to give an **existing type a custom name**.

Think of it as a **nickname** for a type. Instead of writing the same type repeatedly, you create a reusable name and use it throughout your project.

A type alias **does not create a new type**. It simply gives another name (an alias) to an existing type.

---

# 🎯 Why do we use Type Aliases?

Without type aliases, you may end up repeating the same type definitions multiple times.

Using type aliases helps you:

* ✅ Avoid repeating the same type across your codebase (DRY principle).
* ✅ Improve code readability.
* ✅ Make your code easier to maintain.
* ✅ Keep complex types organized.
* ✅ Give meaningful names to types, making your code more self-explanatory.

---

# 📝 Syntax

Type aliases are created using the `type` keyword.

```ts
type User = string;
```

Now, instead of using `string` everywhere, you can use `User`.

```ts
type User = string;

const username: User = "Kaushik";
```

---

# 💡 More Examples

Type aliases can represent much more than primitive types.

## Primitive Type

```ts
type Age = number;
```

---

## Object Type

```ts
type User = {
  name: string;
  age: number;
};
```

---

## Union Type

```ts
type Status = "loading" | "success" | "error";
```

---

## Array Type

```ts
type Numbers = number[];
```

---

## Function Type

```ts
type Add = (a: number, b: number) => number;
```

---

# 🧠 What happens behind the scenes?

Type aliases exist **only in TypeScript**.

During compilation, TypeScript removes all type information.

Example:

```ts
type User = string;

const username: User = "Kaushik";
```

Compiles to:

```js
const username = "Kaushik";
```

Notice that the `type` declaration completely disappears because JavaScript has no concept of type aliases.

---

# 📌 Naming Convention

By convention, type aliases are written in **PascalCase** (also called Upper Camel Case).

```ts
type User = string;
type UserProfile = {};
type ApiResponse = {};
```

❌ Avoid

```ts
type user = string;
type api_response = {};
```

> 💡 This is a convention, not a TypeScript rule, but almost every production codebase follows it.

---

# 🚀 Production Perspective

In large-scale applications, developers use type aliases to:

* 📦 Define API request and response types.
* 👤 Model users, products, and orders.
* 🔄 Reuse common types across multiple files.
* 🧩 Simplify complex union and intersection types.
* 📚 Keep the codebase clean, consistent, and easier to maintain.

Instead of repeating the same object structure everywhere, teams define it once as a type alias and reuse it throughout the project.

---

# 📚 Key Points

✅ A type alias gives a custom name to an existing type.

✅ It helps reduce code duplication and improves readability.

✅ Type aliases can represent primitive types, objects, arrays, functions, tuples, unions, and more.

✅ They exist only during TypeScript compilation.

✅ They are removed completely in the generated JavaScript.

✅ Use **PascalCase** when naming type aliases.

---

# 🎯 Remember

> **Type Alias = A reusable name for an existing type.**
> It improves readability and maintainability but does **not** create a new runtime object.
