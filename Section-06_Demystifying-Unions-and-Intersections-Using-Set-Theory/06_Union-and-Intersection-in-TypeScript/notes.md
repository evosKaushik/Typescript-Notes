# 📝 Union (`|`) and Intersection (`&`) in TypeScript

## 💡 Types are Sets

Since **types are just sets of values**:

- `|` → **Union** (Combine both sets)
- `&` → **Intersection** (Keep only common values)

```ts
type T2 = string | "Hi";
type T3 = string | number;
type T4 = boolean | true;
type T5 = Exclude<boolean, true>;
type T6 = (number | boolean | string) & (boolean | string);
type T7 = string & number;
```

---

## 🌍 `T2`

```ts
type T2 = string | "Hi";
```

`"Hi"` is already a value inside the `string` set.

So,

```ts
type T2 = string;
```

---

## 🔀 `T3`

```ts
type T3 = string | number;
```

This combines both sets.

So,

```ts
type T3 = string | number;
```

A value can be either a `string` or a `number`.

---

## ✅ `T4`

```ts
type T4 = boolean | true;
```

`true` is already part of the `boolean` set.

So,

```ts
type T4 = boolean;
```

---

## ➖ `T5`

```ts
type T5 = Exclude<boolean, true>;
```

`boolean` contains only two values:

```ts
true
false
```

Removing `true` leaves only:

```ts
type T5 = false;
```

> **Note:** This works because `boolean` is a **finite** set with only two values. Types like `string` or `number` have infinitely many possible values.

---

## 🤝 `T6`

```ts
type T6 = (number | boolean | string) & (boolean | string);
```

Intersection (`&`) keeps only the values that exist in **both** sets.

Common types are:

- `boolean`
- `string`

So,

```ts
type T6 = boolean | string;
```

---

## 🚫 `T7`

```ts
type T7 = string & number;
```

No value can be **both** a `string` and a `number` at the same time.

So,

```ts
type T7 = never;
```

---

## 📌 Quick Summary

| Type | Result | Reason |
|------|--------|--------|
| `string \| "Hi"` | `string` | `"Hi"` is already inside `string` |
| `string \| number` | `string \| number` | Union combines both sets |
| `boolean \| true` | `boolean` | `true` is already inside `boolean` |
| `Exclude<boolean, true>` | `false` | Remove `true` from `{true, false}` |
| `(number \| boolean \| string) & (boolean \| string)` | `boolean \| string` | Keep only common values |
| `string & number` | `never` | No common values |