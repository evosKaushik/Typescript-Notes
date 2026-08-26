# 📝 Adding Constraints to Generics

Constraints are a required format in generics which we get

```ts
type MyType<T extends { name: string }> = T;
```

> `{name: string}` should be sub type of T

## Dynamic

```ts
type MyType<T extends U, U> = T; // Ts allow it use because initialize
```
