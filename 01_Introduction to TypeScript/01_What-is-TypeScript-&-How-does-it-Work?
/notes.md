# 📘 What is TypeScript & How Does It Work?

## VS Code Uses TypeScript Behind the Scenes

* VS Code uses **tsserver (TypeScript Language Server)** for:

  * Auto-completion
  * Error detection
  * Hover info
  * Refactoring
  * Go to Definition

---

## Communication Between VS Code & tsserver

* VS Code and tsserver are separate processes.
* They communicate using **IPC (Inter-Process Communication)**.
* Messages are exchanged in **JSON format**.

```text
VS Code ↔ IPC ↔ tsserver
```

---

## Other Languages Do the Same

* HTML → HTML Language Server
* CSS → CSS Language Server
* Python → Pylance
* Rust → rust-analyzer

These run behind the scenes and provide editor intelligence.

---

## Where Does Type Information Come From?

TypeScript reads `.d.ts` (Declaration Files).

They contain:

* Function signatures
* Classes
* Interfaces
* Type definitions

Think of them as **instruction manuals for libraries**.

---

## Type Checking in JavaScript

Enable TypeScript checking in JS files:

```js
// @ts-check
```

This gives TypeScript errors and suggestions inside JavaScript.

---

## Why TypeScript Is Not a Complete Language

TypeScript has:

* ❌ No runtime
* ❌ No VM
* ❌ No execution engine

It must be converted into JavaScript before execution.

```text
TypeScript → JavaScript → Browser / Node.js
```

---

## Why Developers Use TypeScript

* Better IntelliSense
* Early error detection
* Safer refactoring
* Easier maintenance
* Higher productivity
