# 🚀 Initializing a TypeScript Project Using the Init Command

We can initialize a TypeScript project by running:

```bash
tsc --init
```

This creates a `tsconfig.json` file.

---

## 📄 tsconfig.json

The `tsconfig.json` file is used to configure how TypeScript compiles your project.

It contains settings such as:

* Target JavaScript version
* Module system
* Strict mode
* Include/Exclude rules
* And many other compiler options

---

## 👀 Watch Mode (`--watch` Flag)

Instead of running `tsc` manually after every change, we can use **Watch Mode**.

```bash
tsc --watch
```

### Short Hand

```bash
tsc -w
```

Both commands do exactly the same thing.

---

### ✅ What It Does

* Watches project files for changes.
* Automatically recompiles when a file is saved.
* Keeps running until stopped manually.

---

## 🎯 Quick Summary

📌 `tsc --init` → Creates a `tsconfig.json` file

📌 `tsconfig.json` → Stores TypeScript compiler configuration

📌 `tsc --watch` → Watches files and recompiles automatically

📌 `tsc -w` → Short-hand for `--watch`
