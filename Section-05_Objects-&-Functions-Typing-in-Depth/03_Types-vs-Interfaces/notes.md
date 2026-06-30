# Types vs Interfaces

## `type`

A `type` creates a **type alias**.

A type alias gives another name to an existing type.

It can be used for much more than just objects.

Examples:

- Objects
- Primitive types
- Union types
- Intersection types
- Tuples
- Function types
- Conditional types
- Mapped types

```ts
type User = {
  name: string;
  age: number;
};

type ID = string;

type Status = "loading" | "success" | "error";
```

> Although `type` is called a **Type Alias**, it is commonly used to describe object shapes as well.

---

## `interface`

An interface is mainly designed for defining the **shape of objects**.

```ts
interface User {
  name: string;
  age: number;
}
```

Interfaces can also describe:

- Class contracts
- Function object types
- API models
- React props

---

# Naming Convention

Most modern TypeScript projects **do not** prefix names with `I` or `T`.

Recommended:

```ts
interface User {}

type Status = "success" | "error";
```

Older codebases may use:

```ts
interface IUser {}

type TUser = {};
```

However, this naming style is becoming less common.

Follow your team's coding style instead of creating your own.

---

# Interface Declaration Merging

One powerful feature of interfaces is **declaration merging**.

If two interfaces have the same name, TypeScript automatically merges them.

```ts
interface User {
  name: string;
}

interface User {
  age: number;
}
```

TypeScript treats it as:

```ts
interface User {
  name: string;
  age: number;
}
```

Type aliases **cannot** do this.

```ts
type User = {
  name: string;
};

type User = {
  age: number;
};
// ❌ Error
```

---

# Extending Types and Interfaces

Interfaces extend other interfaces using `extends`.

```ts
interface Person {
  name: string;
}

interface Student extends Person {
  rollNo: number;
}
```

Type aliases can create new types by using intersections (`&`).

```ts
type Person = {
  name: string;
};

type Student = Person & {
  rollNo: number;
};
```

You can also extend object types with `extends` when using interfaces.

---

# Is `&` slower than `extends`?

For almost every project, **no**.

The performance difference is extremely small and is not something developers optimize for.

For larger project different can be seen

Choose based on readability and the type you are modeling, **not** performance.

---

# Production Practice

Use **interface** when:

- Modeling object shapes
- Public APIs
- Class contracts
- Data models

Use **type** when:

- Union types
- Intersection types
- Tuples
- Conditional types
- Mapped types
- Primitive aliases

Many large TypeScript codebases use **both** depending on the problem being solved.

---

# Key Points

- `type` creates a type alias and supports many kinds of types.
- `interface` is mainly used for object structures.
- Interfaces support **declaration merging**.
- Type aliases do **not** support declaration merging.
- Interfaces use `extends`; type aliases combine object types using `&`.
- Modern TypeScript generally avoids prefixes like `IUser` and `TUser` unless required by a project's coding standards.