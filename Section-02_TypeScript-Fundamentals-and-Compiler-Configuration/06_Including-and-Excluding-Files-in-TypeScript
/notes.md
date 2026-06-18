# 📂 Including and Excluding Files in TypeScript

## 🌟 Glob Patterns

A **glob pattern** is a special pattern used to match files and folders using wildcards.

---

| Pattern | Meaning                                     | Example                                                                        |
| ------- | ------------------------------------------- | ------------------------------------------------------------------------------ |
| `*`     | Matches any number of characters except `/` | `./*.ts` → Matches all `.ts` files in the current folder                       |
| `**`    | Matches folders recursively                 | `./**/*.ts` → Matches all `.ts` files in the current folder and all subfolders |
| `?`     | Matches exactly one character               | `./test?.ts` → Matches `test1.ts`, `testA.ts`, `testX.ts` but not `test10.ts`  |

---

## 📁 Example Folder Structure

```txt
src/
├── index.ts
├── app.ts
├── test1.ts
├── test10.ts
└── utils/
    └── helper.ts
```

---

### `./*.ts`

Matches:

```txt
index.ts
app.ts
test1.ts
test10.ts
```

---

### `./**/*.ts`

Matches:

```txt
index.ts
app.ts
test1.ts
test10.ts
utils/helper.ts
```

---

### `./test?.ts`

Matches:

```txt
test1.ts
```

Does NOT match:

```txt
test10.ts
```

---

# 📥 Including Files

By default, `tsc` compiles all TypeScript files in the project (except some automatically ignored folders like `node_modules`).

Use the `include` property to compile only specific files or folders.

```json
{
  "compilerOptions": {},
  "include": ["./*.test.ts"]
}
```

### ✅ Result

Only files matching:

```txt
example.test.ts
user.test.ts
auth.test.ts
```

will be compiled.

---

# 🚫 Excluding Files

Use the `exclude` property to tell TypeScript which files or folders should NOT be compiled.

```json
{
  "compilerOptions": {},
  "exclude": ["./*.test.ts"]
}
```

### ✅ Result

Files matching:

```txt
example.test.ts
user.test.ts
auth.test.ts
```

will be ignored by the compiler.

---

# 🚫 Common Exclusions

```json
{
  "compilerOptions": {},
  "exclude": [
    "node_modules",
    "dist",
    "build"
  ]
}
```

These folders usually contain dependencies or generated files that do not need recompilation.

---

# ⚠️ Important

Notice that it is:

```json
{
  "compilerOptions": {}
}
```

✅ Correct: `compilerOptions`

❌ Wrong: `compilerOption`

The property name must be plural.

---

# 📝 Notes

* `include` = Compile ONLY these files.
* `exclude` = Ignore these files during compilation.
* Both accept arrays of glob patterns.
* Glob patterns help TypeScript find matching files and folders.

---

# 🎯 Quick Summary

📌 `*` → Match files in the current folder

📌 `**` → Match files recursively in all subfolders

📌 `?` → Match exactly one character

📌 `include` → Files TypeScript should compile

📌 `exclude` → Files TypeScript should ignore

📌 `compilerOptions` → Configuration options for the TypeScript compiler

---

## 🎉 Easy Analogy

Think of `tsc` as a security guard at a party:

* ✅ `include` = Guest list (who can enter)
* 🚫 `exclude` = Block list (who cannot enter)
* 🎉 `tsc` = Security guard checking the lists before allowing files into the compilation process
