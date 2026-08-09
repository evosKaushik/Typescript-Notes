# 📝 Union and Intersection with Conflicting Property Types

Two object types can have the same property but **different types**.

```ts
type Person1 = {
    name: string;
    age: number;
}

type Person2 = {
    name: string;
    age: string;
}
```

## 🔀 Union `|`

```ts
type Person = Person1 | Person2;
```

For `name`:

```text
string | string → string
```

For `age`:

```text
number | string → number | string
```

So conceptually:

```ts
type Person = {
    name: string;
    age: number | string;
}
```

Union means **OR** — `age` can be either `number` or `string`.

---

## 🤝 Intersection `&`

```ts
type Person = Person1 & Person2;
```

For `name`:

```text
string & string → string
```

For `age`:

```text
number & string → never
```

So conceptually:

```ts
type Person = {
    name: string;
    age: never;
}
```

`age` becomes `never` because there is **no value that can be both a `number` and a `string`**.

---

## 🧠 Set Thinking

```text
| → OR  → combine possible values
& → AND → find common values

number | string → number | string
number & string → never
```

```text
number ∩ string = ∅
                  ↓
                never
```

`never` = **empty set**
