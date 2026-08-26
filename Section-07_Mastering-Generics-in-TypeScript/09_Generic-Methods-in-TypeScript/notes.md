# 📝 Generic Methods in TypeScript

We can add Generic Methods in Ts

```ts
const store = {
  list: [],
  getUser<T>(user: T[]) {
    T.toString();
  },
};
```

aur create a interface

```ts
interface Types<T> {
    lists: T[],
    getUser<U>(user: U[]) {
    U.toString();
  },
}
```
