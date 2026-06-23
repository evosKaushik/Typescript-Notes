# 📚 Array Methods in TypeScript

Array methods are powerful because TypeScript can often **infer the return type automatically** based on what you return from the callback.

---

# 🗺️ `map()`

`map()` creates a **new array**.

The type of the new array depends on **what you return** from the callback.

```ts
const array = [1, 2, 3, 4, 5, 6]

const result = array.map(el => el % 2 === 0)
```

### Return Type

```ts
boolean[]
```

Because:

```ts
el % 2 === 0
```

returns a boolean (`true` or `false`).

Result:

```ts
[false, true, false, true, false, true]
```

---

### Another Example

```ts
const numbers = [1, 2, 3]

const result = numbers.map(el => el.toString())
```

Return Type:

```ts
string[]
```

💡 Rule:

> `map()` returns an array whose type is determined by the callback's return value.

---

# 🔍 `filter()`

`filter()` creates a new array containing only the elements that pass a condition.

```ts
const array = [1, 2, 3, 4, 5, 6]

const result = array.filter(el => el % 2 === 0)
```

### Return Type

```ts
number[]
```

Result:

```ts
[2, 4, 6]
```

The callback returns a boolean:

```ts
el % 2 === 0
```

But the final array still contains the original elements.

💡 Rule:

> `filter()` returns the same element type as the original array, just with some values removed.

---

### Example

```ts
const users = ["Kaushik", "Rahul", "Aman"]

const result = users.filter(user => user.length > 5)
```

Return Type:

```ts
string[]
```

---

# ➕ `reduce()`

`reduce()` combines all elements into a single value.

The return type depends on:

1. The initial value.
2. What you return from the accumulator (`acc`).

---

### Sum Example

```ts
const array = [1, 2, 3, 4]

const total = array.reduce(
  (acc, curr) => acc + curr,
  0
)
```

Return Type:

```ts
number
```

Because:

```ts
0
```

is a number and we keep returning numbers.

---

### Object Example

```ts
const array = [1, 2, 3]

const result = array.reduce(
  (acc, curr) => {
    acc[curr] = curr * 2
    return acc
  },
  {} as Record<number, number>
)
```

Return Type:

```ts
Record<number, number>
```

Because the accumulator starts as an object.

---

# 📝 Quick Revision

## `map()`

```ts
const result = array.map(el => el % 2 === 0)
```

✅ Return Type:

```ts
boolean[]
```

**Type depends on what you return.**

---

## `filter()`

```ts
const result = array.filter(el => el % 2 === 0)
```

✅ Return Type:

```ts
number[]
```

**Returns the same array element type, but filtered.**

---

## `reduce()`

```ts
const result = array.reduce(
  (acc, curr) => acc + curr,
  0
)
```

✅ Return Type:

```ts
number
```

**Depends on the accumulator type and what you return.**

---

# 🔥 Easy Way to Remember

### `map()`

> Transform each item → Return type changes.

```ts
number[] → string[]
number[] → boolean[]
```

---

### `filter()`

> Keep or remove items → Type usually stays the same.

```ts
number[] → number[]
string[] → string[]
```

---

### `reduce()`

> Combine everything into one value.

```ts
number[] → number
number[] → object
number[] → string
```

The final type depends on the accumulator (`acc`) and the value returned from the callback.
