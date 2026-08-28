# 📝 Recursive Generics in TypeScript

## For create Recursive Generics we call generic inside generic

```ts 
type DynamicType<T> = {
  child: DynamicType<T>
} // we have to define infinite time

type Tree<T> = {
  child?: Tree<T>
} // optional create we can stop at a nested point and not give error

```