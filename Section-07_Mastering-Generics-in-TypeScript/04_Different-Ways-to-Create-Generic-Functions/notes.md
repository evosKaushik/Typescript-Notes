# 📝 Different Ways to Create Generic Functions

## Syntax
```ts 
function fun<T>(argv: T): T {
  return argv;
}

const fun = function <T>(argv: T): T {
  return argv;
};

const fun = <T>(argv: T): T => {
  return argv;
};

type FunType = <T>(a: T) => T;

interface FunType {
  <T>(a: T): T;
}

const fun: FunType = function (a) {
  return a;
};

let value = fun<true>(true);
```

