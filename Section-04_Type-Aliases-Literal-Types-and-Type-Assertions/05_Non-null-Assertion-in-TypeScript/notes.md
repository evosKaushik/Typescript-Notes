# Non-null Assertion in TypeScript

## 📌 Topic
**TypeScript → Non-null Assertion Operator**

---

# What is the Non-null Assertion Operator?

The **Non-null Assertion Operator** (`!`) is a TypeScript operator that tells TypeScript:

> **"Trust me, this value is not `null` or `undefined`."**

It only affects TypeScript's type checking and does **not** perform any runtime check.

---

# Syntax

```ts
variableName!
```

Example:

```ts
const input = document.querySelector("input");

input!.focus();
```

Normally, TypeScript infers:

```ts
HTMLInputElement | null
```

After writing:

```ts
input!
```

TypeScript assumes the value is:

```ts
HTMLInputElement
```

and allows you to access its methods without errors.

---

# Why do we need it?

Sometimes TypeScript cannot guarantee that a value exists, even though you know it will exist when the code runs.

For example:

```ts
let username: string | undefined;

username = "Kaushik";

printName(username!);

function printName(name: string) {
  console.log(name.toUpperCase());
}
```

Without `!`, TypeScript complains because `username` could be `undefined`.

Using `!` tells TypeScript that the value is definitely available.

---

# When should you use it?

You should **avoid using the Non-null Assertion Operator whenever possible.**

Use it only when you are completely sure that the value cannot be `null` or `undefined`.

Common situations include:

- After checking that a value exists.
- When working with DOM elements that you know are present.
- In asynchronous code where a value is initially `undefined` but is guaranteed to be assigned before it is used.

Example:

```ts
let user: string | undefined;

async function loadUser() {
  user = "Kaushik";
}

await loadUser();

console.log(user!.toUpperCase());
```

Here, after `loadUser()` finishes, we know `user` has a value, even if TypeScript cannot prove it.

---

# Be Careful ⚠️

The `!` operator only removes the TypeScript error.

It **does not** check the value at runtime.

Example:

```ts
const value: string | undefined = undefined;

console.log(value!.toUpperCase());
```

TypeScript compiles this successfully.

However, at runtime, it throws an error because `value` is actually `undefined`.

Always use `!` only when you are certain the value exists.

---

# Key Points 📝

- `!` is called the **Non-null Assertion Operator**.
- Use optional chaining instead as it return undefined
- It tells TypeScript that a value is **not** `null` or `undefined`.
- It only affects TypeScript's type checking.
- It performs **no runtime validation**.
- Use it sparingly and only when you are completely sure the value exists.
- Incorrect use can lead to runtime errors.