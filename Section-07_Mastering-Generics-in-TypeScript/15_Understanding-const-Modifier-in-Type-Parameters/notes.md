# 📝 Understanding const Modifier in Type Parameters

## if we have to assign a const with generics as it only infers the types to variables which is done by `as const` which do strict type we can do same in generic also only works which classes & Function

```ts
function myFunc<const T>(value: T) {
  return value;
}

const a = myFunc([1,2,3,4]) // type will be [1,2,3,4] readonly
```
