# 📝 Typing Rest Parameters in TypeScript

## Syntax

```ts
function numbers(...numbers: number[]) {
  console.log(numbers);
}
```

The rest parameter is typed by specifying the type of the array it collects.

---

## Variations

Rest parameters can also be used with:

- Union types
- Tuple types
- Required parameters before the rest parameter

Example:

```ts
function greet(name: string, ...messages: string[]) {
  console.log(name, messages);
}
```