# 📝 Working with Nested Generics

```ts
type DynamicType<T> = {
  value: T;
};

const value: DynamicType<DynamicType<string>>;
```

#### Here we can add multiple generic into the generic to make it nested route

### so the type of value will be
```ts
{
  value: {
    value: string
  }
}
```