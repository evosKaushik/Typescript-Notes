# 🐛 Debugging TypeScript Applications

## Run & Debug with Node.js

To debug a TypeScript application, you can set **breakpoints** in your code.

A breakpoint tells the debugger:

> "Pause execution here so I can inspect variables and program state."

This helps you:

* Check variable values
* Follow code execution step-by-step
* Find bugs more easily

---

## Debugging in Browser DevTools

### Enable Source Maps

In `tsconfig.json`:

```json
{
  "compilerOptions": {
    "sourceMap": true
  }
}
```

---

## Why Source Maps Are Needed

Browsers cannot execute TypeScript directly.

TypeScript is first transpiled into JavaScript:

```text
TypeScript (.ts)
        ↓
     tsc
        ↓
JavaScript (.js)
```

Without source maps, browser DevTools can only show the generated JavaScript.

With `sourceMap: true`, TypeScript generates `.map` files that connect the JavaScript code back to the original TypeScript source.

As a result, you can:

* Set breakpoints in `.ts` files
* View original TypeScript code in DevTools
* Debug TypeScript instead of generated JavaScript

---

## 📝 Summary

* Use breakpoints to pause execution during debugging.
* Browsers cannot run TypeScript directly.
* TypeScript is transpiled into JavaScript before execution.
* `sourceMap: true` generates source maps (`.map` files).
* Source maps allow DevTools to debug the original TypeScript code.
