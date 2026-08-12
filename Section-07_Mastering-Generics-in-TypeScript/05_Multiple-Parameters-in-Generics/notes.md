# 📝 Multiple Parameters in Generics

## Syntax

```ts
type DynamicMultipleParameters<T, U> = T & U;
type DynamicMultipleParameters<T, U> = [T, U];

const a: DynamicMultipleParameters<string, number> = ["string", 123];

// Function

function getTuple<T, U>(a: T, b: U): [T, U] {
  return [a, b];
}

let tuple= getTuple<string, number>("x": 12);

```
