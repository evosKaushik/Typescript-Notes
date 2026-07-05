# Module Detection in TypeScript

## What is Module Detection?

`moduleDetection` is a compiler option in `tsconfig.json`.

It tells TypeScript **how to determine whether a file should be treated as a module or a script.**

```json
{
  "compilerOptions": {
    "moduleDetection": "auto" // auto (default), legacy, force
  }
}
```

> **Note:** `moduleDetection` only decides whether a file is a **module** or a **script**. It does **not** control how JavaScript modules are generated. That is handled by the `module` compiler option.

---

# Modes

## 1. auto (Default)

This is the default mode.

TypeScript automatically determines whether a file is a module.

A file is usually considered a module if it contains:

- `import`
- `export`
- Other environment-specific module indicators (depending on the module system, such as Node.js settings).

Example:

```ts
import { add } from "./math";

console.log(add(2, 3));
```

Since the file contains an `import`, TypeScript treats it as a **module**.

---

## 2. legacy

This uses the older TypeScript behavior.

A file is treated as a module **only if it contains an `import` or `export` statement.**

If there is no `import` or `export`, the file is treated as a global script.

Example:

```ts
const message = "Hello";
```

This file is treated as a **script**, not a module.

---

## 3. force

In this mode, TypeScript treats **every file as a module**, even if it has no `import` or `export` statements.

Example:

```ts
const count = 10;
```

Even though there are no imports or exports, the file is still considered a **module**.

This helps avoid accidental global variables and is useful in modern TypeScript projects.

---

# Summary

| Mode | Behavior |
|------|----------|
| `auto` | Automatically detects whether a file is a module (default). |
| `legacy` | Only files with `import` or `export` are modules. Otherwise, they are scripts. |
| `force` | Every file is treated as a module, regardless of its contents. |

---

## Key Points

- `moduleDetection` determines whether a file is a **module** or a **script**.
- It **does not** control the generated JavaScript module format.
- The JavaScript module format (`ESNext`, `CommonJS`, `NodeNext`, etc.) is controlled by the `module` compiler option.
- Most modern TypeScript projects use the default `auto` mode.