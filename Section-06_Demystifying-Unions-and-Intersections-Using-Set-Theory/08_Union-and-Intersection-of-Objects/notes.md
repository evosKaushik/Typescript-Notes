# 📝 Union and Intersection of Objects

Just like normal types:

- `|` → **Union**
- `&` → **Intersection**

The same idea works with **object types** too.

---

## 🔀 Union of Objects `|`

```ts
type T1 = { length: number }
type T2 = { length: number; name: string }

const obj: T1 | T2 = {
    length: 80,
    name: "hello",
}
```

Here:

```ts
T1 = { length: number }

T2 = { length: number; name: string }
```

The value can be:

```text
T1 OR T2
```

So TypeScript only guarantees the properties that **both types have in common**.

Both have:

```ts
length: number
```

Therefore:

```ts
obj.length // ✅
```

But `name` is not guaranteed:

```ts
obj.name // ❌
```

Why?

Because the value could technically be only a `T1`:

```ts
const obj: T1 | T2 = {
    length: 80
}
```

There is no `name` in `T1`.

### 🧠 Easy Rule

> **Union `|` → What is common is guaranteed.**

```text
T1
┌─────────────────┐
│ length          │
└─────────────────┘

T2
┌─────────────────┐
│ length          │
│ name            │
└─────────────────┘

      ↓ UNION ↓

Guaranteed:
┌─────────────────┐
│ length          │
└─────────────────┘
```

---

## 🤝 Intersection of Objects `&`

```ts
type T1 = { length: number }
type T2 = { length: number; name: string }

const obj: T1 & T2 = {
    length: 80,
    name: "hello",
}
```

`&` means:

```text
T1 AND T2
```

So the value must satisfy **both types at the same time**.

Therefore it must have:

```ts
length: number
name: string
```

So both are available:

```ts
obj.length // ✅
obj.name   // ✅
```

And both are **required**.

This would give an error:

```ts
const obj: T1 & T2 = {
    length: 80
}
// ❌ name is missing
```

### 🧠 Easy Rule

> **Intersection `&` → You must satisfy both types.**

```text
T1
┌─────────────────┐
│ length          │
└─────────────────┘

T2
┌─────────────────┐
│ length          │
│ name            │
└─────────────────┘

       ↓ AND ↓

Required:
┌─────────────────┐
│ length          │
│ name            │
└─────────────────┘
```

---

## 📌 Union vs Intersection

| | Union `\|` | Intersection `&` |
|---|---|---|
| Meaning | OR | AND |
| Example | `T1 \| T2` | `T1 & T2` |
| What is guaranteed? | Common properties | Properties from both |
| `length` | ✅ | ✅ |
| `name` | ❌ Not guaranteed | ✅ Required |

### 🎯 Remember

```text
|  → OR  → Common things are guaranteed

&  → AND → Everything is required
```

So:

```ts
T1 | T2
```

means:

> "It can be either one."

While:

```ts
T1 & T2
```

means:

> "It must satisfy both."