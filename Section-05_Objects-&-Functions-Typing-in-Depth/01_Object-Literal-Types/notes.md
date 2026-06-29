# Object Literal Types

## What are Object Literal Types?

When we create an object, **TypeScript automatically infers its type**. This process is called **Type Inference**.

Example:

```ts
const user = {
  name: "Kaushik",
  age: 16,
  isStudent: true,
};
```

TypeScript infers the type as:

```ts
{
  name: string;
  age: number;
  isStudent: boolean;
}
```

---

## Explicitly Defining Object Types

Instead of relying on type inference, we can explicitly define the object's type.

```ts
const user: {
  name: string;
  age: number;
  isStudent: boolean;
} = {
  name: "xyz",
  age: 52,
  isStudent: true,
};
```

Here, we manually tell TypeScript what the object's structure should be.

---

## Object Type Syntax

Inside an object type, you can separate properties using:

- `;` (Recommended ✅)
- `,`
- New lines

Example:

```ts
{
  name: string;
  age: number;
  isStudent: boolean;
}
```

Although commas also work, **TypeScript itself displays object types using semicolons (`;`)**, so it is considered the standard style.

---

## Creating Reusable Object Types

Instead of writing the same object type repeatedly, create a custom type using the `type` keyword.

```ts
type User = {
  name: string;
  age: number;
  isStudent?: boolean; // optional mean it do undefined | boolean
};

const user: User = {
  name: "xyz",
  age: 52,
  isStudent: true, 
};
```

### Benefits

- Reusable
- Easier to read
- Easier to maintain
- Avoids duplication

---

# `as const`

The `as const` keyword makes an object **deeply readonly** and changes its property types to their exact **literal values**.

Example:

```ts
const user = {
  name: "Kaushik",
  age: 16,
} as const;
```

The inferred type becomes:

```ts
{
  readonly name: "Kaushik";
  readonly age: 16;
}
```

Notice:

- `string` becomes `"Kaushik"`
- `number` becomes `16`
- Every property becomes `readonly`

---

## Why `as const` doesn't work with explicit object types

```ts
const user: {
  name: string;
} = {
  name: "Kaushik",
} as const;
```

Here, `as const` has almost no effect.

Why?

Because the explicit type annotation (`name: string`) **overrides TypeScript's inference**.

TypeScript already knows the type should be `string`, so it widens `"Kaushik"` to `string`.

---

## Correct way to use `as const`

Let TypeScript infer the object first.

```ts
const user = {
  name: "Kaushik",
  age: 16,
} as const;
```

Now `as const` can preserve the literal values and make the object readonly.

---

## Production Practice

In production code:

- Use **type inference** whenever TypeScript can infer the correct type.
- Create reusable types using `type` (or `interface` for object shapes).
- Use `as const` only when you need immutable objects or literal types (such as API endpoints, configuration objects, Redux action types, etc.).
- Avoid combining explicit type annotations with `as const` unless you have a specific reason, because it often defeats the purpose of `as const`.

---

## Key Points

- Object Literal Types describe the shape of an object.
- TypeScript automatically infers object types.
- You can explicitly define an object's type using `:`.
- Use `type` to create reusable object types.
- TypeScript recommends using `;` inside object type definitions.
- `as const` works best when TypeScript is allowed to infer the object's type.
- Explicit type annotations usually prevent `as const` from preserving literal types.