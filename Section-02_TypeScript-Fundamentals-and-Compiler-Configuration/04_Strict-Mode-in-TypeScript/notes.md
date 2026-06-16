# 📘 TypeScript Strict Mode

## ❌ What Strict Mode Is Not

TypeScript's `strict` mode is **not the same as JavaScript's `"use strict"`**.

`"use strict"` affects JavaScript runtime behavior, while TypeScript's `strict` mode improves type checking during compilation.

---

## ✅ What Strict Mode Actually Does

Enable it in `tsconfig.json`:

```json
{
  "compilerOptions": {
    "strict": true
  }
}
```

`strict` is a **master switch** that enables multiple strict type-checking rules behind the scenes.

---

## Some of them are

### `strictNullChecks`

**true**
- `null` and `undefined` are treated as separate types.
- Prevents assigning them to other types unless explicitly allowed.

**false**
- Allows `null` and `undefined` to be assigned to most types.
- Skips many null-safety checks.

---

### `noImplicitAny`

**true**
- Prevents TypeScript from silently using the `any` type.
- Forces you to explicitly define types when TypeScript cannot infer them.

Example:

```ts
function greet(name) {
  return "Hello " + name;
}
```

❌ Error: Parameter `name` implicitly has type `any`.

---

## 🎯 Why Use Strict Mode?

- Catches bugs earlier
- Improves type safety
- Provides better IntelliSense
- Reduces runtime errors

---

## 📝 Summary

- `strict` ≠ `"use strict"`
- `strict` is a compile-time TypeScript feature
- Acts as a master switch for stricter type-checking rules
- Recommended for almost all TypeScript projects