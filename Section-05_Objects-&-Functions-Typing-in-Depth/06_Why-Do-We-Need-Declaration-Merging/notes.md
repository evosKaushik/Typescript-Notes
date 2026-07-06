# 📝 Why Do We Need Declaration Merging?

## What is Declaration Merging?

Declaration Merging is a TypeScript feature that allows multiple declarations with the **same name** to be combined into a single declaration.

This is especially useful when working with **libraries** whose type definitions you cannot modify directly.

---

## Why is it Needed?

Sometimes a library already defines an interface, but you want to add your own custom properties without editing the library's source code.

Instead of modifying the original interface, you can create another interface with the **same name**, and TypeScript automatically merges them.

### Example

```ts
interface LibraryType {
  customType: string;
}
```

If `LibraryType` already exists in a library, the above declaration adds `customType` to it instead of replacing it.

> 💡 This is one of the main reasons declaration merging exists—it lets you safely extend existing types.

---

## Real-World Example

When you use **VS Code**, you get IntelliSense (autocomplete) for objects like:

- `window`
- `document`
- `navigator`
- `console`

These types are **not built into VS Code itself**.

They come from TypeScript's type definition files (`.d.ts`) that are installed inside `node_modules`.

For example:

```text
node_modules/
└── typescript/
```

or

```text
node_modules/
└── @types/
```

These declaration files define the interfaces for browser APIs.

---

## Why Interfaces Are Used

In TypeScript's standard library, **interfaces** are commonly used for **object types** because they support declaration merging.

Example:

```ts
interface Window {
  myCustomProperty: string;
}
```

This extends the existing `Window` interface instead of replacing it.

---

## Why Not Use `type`?

`type` aliases **cannot** be declaration merged.

They are mainly used for:

- Union types
- Intersection types
- Function types
- Tuple types
- Complex type compositions

Example:

```ts
type Status = "loading" | "success" | "error";
```

Because `type` cannot merge, libraries generally use **interfaces for object shapes** that users may want to extend.

---

## 📌 Key Points

- Declaration Merging combines multiple declarations with the same name.
- It is mainly used to extend library types without modifying the library.
- Browser objects like `window` and `document` are defined using declaration files (`.d.ts`).
- Interfaces are preferred for object types because they support declaration merging.
- `type` aliases are commonly used for unions, intersections, tuples, and function types, but they **cannot** be merged.