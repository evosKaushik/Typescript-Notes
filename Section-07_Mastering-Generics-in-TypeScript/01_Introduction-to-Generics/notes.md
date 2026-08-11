# 📝 Introduction to Generics

## What are Generics?

**Generics** allow us to create a type that can work with different types.

Think of `T` like a **function parameter**, but for types.

```ts
type DynamicType<T> = T;
```

Here `T` is a **type parameter**.

```ts
const a: DynamicType<string> = "Hello";
const b: DynamicType<number> = 123;
const c: DynamicType<string | boolean> = true;
```

```text
DynamicType<string>
        ↓
      T = string

DynamicType<number>
        ↓
      T = number
```

## 🧠 Think Like a Function

A normal function accepts values:

```ts
function identity(value: number) {
    return value;
}
```

A generic accepts a **type**:

```ts
type DynamicType<T> = T;
```

Think of it like:

```text
DynamicType<T>
      ↓
T is a type parameter
      ↓
Give T a type
      ↓
DynamicType<string>
```

## 🔢 Multiple Type Parameters

Generics can accept multiple type parameters.

```ts
type DynamicType<T, T1> = {
    isOk: T;
    data: T1;
};
```

```ts
const result: DynamicType<boolean, string> = {
    isOk: true,
    data: "Hello",
};
```

Here:

```text
T  → boolean
T1 → string
```

So the resulting type becomes:

```ts
{
    isOk: boolean;
    data: string;
}
```

## 📌 Syntax

```ts
type TypeName<T> = T;
```

```ts
type TypeName<T, T1, T2> = {
    value: T;
    data: T1;
    extra: T2;
};
```

## 🧠 Remember

> **Generics = Type parameters**

Just like a function receives a value:

```ts
function test(value) {}
```

A generic receives a type:

```ts
type Test<T> = T;
```

`T` is just a name. You can use other names too:

```ts
type Test<Type> = Type;
```
