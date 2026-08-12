# 📝 Generic Functions in TypeScript

Syntax
```ts 
function test<T>(argument: T): T{ // the function have X type it will argument will be X and Return the X type
    // Here any logic and we return at the end
    return argument
}


test(true) // if we not pass it infer if it is any string aur number it will become literal 
test<"Fruit" | "Vegetable">("Vegetable") // aur we can pass custom types as shown in <type>
```

