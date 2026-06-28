# Type Assertions in TypeScript

## 📌 Topic
**TypeScript → Type Assertions**

---

# Why do we need Type Assertions?

Sometimes TypeScript cannot correctly infer the type of a value.

This mostly happens when working with:
- Arrays containing multiple data types
- Values coming from external libraries
- DOM elements
- Unknown or any types

In these situations, TypeScript cannot provide proper IntelliSense (method suggestions).

To tell TypeScript what the actual type is, we use **Type Assertions**.

---

# Syntax

```ts
value as DataType
```

Example:

```ts
const randomArr = [1, "Hi", true, "Hello"];

(randomArr[1] as string).toUpperCase();
```

Without the assertion, TypeScript only knows that:

```ts
randomArr[1]
```

could be multiple types.

After writing:

```ts
randomArr[1] as string
```

TypeScript now assumes it is a string and gives all string method suggestions like:

- `toUpperCase()`
- `toLowerCase()`
- `trim()`
- `includes()`

---

# Important

When using:

```ts
as
```

you are basically telling TypeScript:

> **"Trust me, I know this value is of this type."**

TypeScript does **not** verify whether you are actually correct.

Example:

```ts
const value = 10 as unknown as string;
```

TypeScript accepts this.

But at runtime:

```ts
value.toUpperCase();
```

will throw an error because the actual value is still a number.

So always use type assertions carefully.

---

# Custom Types

Type assertions can also be used with your own custom types.

Example:

```ts
type User = {
  name: string;
};

const data = {} as User;
```

---

# `as const`

TypeScript also provides another assertion:

```ts
as const
```

It is mainly used with:

- Arrays
- Objects

Normally TypeScript widens values.

Example:

```ts
const name = "Kaushik";
```

TypeScript infers:

```ts
string
```

instead of the literal type:

```ts
"Kaushik"
```

`as const` prevents this widening.

---

# `as const` with Arrays

Example:

```ts
const colors = ["red", "blue"] as const;
```

TypeScript converts it into:

```ts
readonly ["red", "blue"]
```

This means:

- Values become literal types.
- The array becomes readonly.
- You cannot push, pop, or modify elements.

---

# `as const` with Objects

Example:

```ts
const user = {
  name: "Kaushik",
  age: 16,
} as const;
```

TypeScript infers:

```ts
{
  readonly name: "Kaushik";
  readonly age: 16;
}
```

Notice two things happen:

- Every property becomes **readonly**.
- Every value becomes its **literal type**.

---

# `as const` vs `Object.freeze()`

Although they look similar, they are different.

### `as const`

- TypeScript feature
- Works only during development
- Gives readonly types
- Converts values to literal types
- Has no effect at runtime

### `Object.freeze()`

- JavaScript feature
- Works at runtime
- Prevents object modification
- Does not improve TypeScript's type inference by itself

---

# Key Points 📝

- Use `as` when TypeScript cannot infer the correct type.
- `as` only changes TypeScript's understanding—it does **not** change the actual value.
- Wrong assertions may compile successfully but fail at runtime.
- `as const` prevents type widening.
- `as const` makes arrays and objects readonly.
- `as const` also converts values into literal types.