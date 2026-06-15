# 📘 Configuring the TypeScript Compiler

## 📄 Configuration Files

### JavaScript Projects

Use:

```json
{
  "compilerOptions": {}
}
```

File:

```text
jsconfig.json
```

-> Uses the TypeScript language server behind the scenes.
-> Provides IntelliSense, autocomplete, navigation, and type checking for JavaScript projects.

---

### TypeScript Projects

Use:

```text
tsconfig.json
```

-> Controls how TypeScript compiles code.
-> Provides additional compiler configuration options.

---

# ⚙️ compilerOptions

Example:

```json
{
  "compilerOptions": {
    "target": "es6",
    "removeComments": true,
    "noEmitOnError": true,
    "pretty": true,
    "outDir": "./dist",
    "rootDir": "./src"
  }
}
```

---

## 🎯 target

```json
{
  "target": "es6"
}
```

-> Specifies which JavaScript version TypeScript should compile to.

Examples:

```text
es3 // removed
es5 // deprecated/removed in TS  v6
es6
es2017
es2020  
esnext
```

---

## 🗑️ removeComments

```json
{
  "removeComments": true
}
```

-> Removes comments from the generated JavaScript output.

Default:

```text
false
```

---

## ❌ noEmitOnError

```json
{
  "noEmitOnError": true
}
```

-> Prevents JavaScript files from being generated if compilation errors exist.

Default:

```text
false
```

---

## ✨ pretty

```json
{
  "pretty": true
}
```

-> Displays compiler errors in a more readable and colorful format.

Default:

```text
true
```

---

## 📂 outDir

```json
{
  "outDir": "./dist"
}
```

-> Specifies where compiled JavaScript files will be generated.

Example:

```text
src/index.ts
        ↓
dist/index.js
```

Default:

```text
Current working directory
```

---

## 📁 rootDir

```json
{
  "rootDir": "./src"
}
```

-> Specifies where the main TypeScript source files are located.

Example:

```text
project/
├── src/
│   ├── index.ts
│   └── app.ts
└── dist/
```

Default:

```text
Current working directory
```

---

# 📝 Notes

✅ `jsconfig.json` is mainly for JavaScript projects.

✅ `tsconfig.json` is for TypeScript projects.

✅ `target` controls the JavaScript version generated.

✅ `removeComments` removes comments from output files.

✅ `noEmitOnError` prevents output generation when errors exist.

✅ `pretty` improves compiler error readability.

✅ `rootDir` specifies the source folder.

✅ `outDir` specifies the output folder.

### One-Line Summary

> `tsconfig.json` allows you to control how TypeScript compiles and organizes your project.
