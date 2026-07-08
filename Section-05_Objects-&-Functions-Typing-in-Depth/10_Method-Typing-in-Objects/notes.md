# 📝 Method Typing in Objects

There are **two ways** to define the type of a method in an object or interface.

```ts
interface User {
  firstName: string;
  lastName: string;

  // Function type (arrow function syntax)
  getFullName: () => string;

  // Method syntax (recommended)
  getFullName(): string;
}

const user: User = {
  // ...
};
```

## Key Points

- `getFullName: () => string` uses **function type syntax**.
- `getFullName(): string` uses **method syntax**.
- TypeScript generally recommends using **method syntax** for methods inside interfaces and object types.