# 📝 Built-in Generics in TypeScript

## Built-in Generic Types

### 1. Array

```ts
const arr = new Array<boolean>();

arr.push(true);
```

`string[]` is equivalent to `Array<string>`:

```ts
const names: string[] = [];
const names2: Array<string> = [];
```

---

### 2. Set

Stores unique values.

```ts
const set = new Set<string>();

set.add("Hi");
set.add("Hello");
```

---

### 3. Map

Stores key-value pairs.

```ts
const map = new Map<string, number>();

map.set("age", 15);
```

`Map<K, V>` → `K` = Key type, `V` = Value type.

---

### 4. Promise

Represents a future value.

```ts
const promise: Promise<string> = fetchData();

async function fetchData(): Promise<string> {
  return "Hello";
}
```

---

### 5. Readonly

Makes object properties readonly.

```ts
const user: Readonly<{ name: string; age: number }> = {
  name: "Kaushik",
  age: 15
};

user.age = 16; // ❌
```

---

### 6. ReadonlyArray

Makes an array readonly.

```ts
const numbers: ReadonlyArray<number> = [1, 2, 3];

numbers.push(4); // ❌
```

---

## ⭐ Other Useful Built-in Generic Utility Types

### Record

```ts
const users: Record<string, number> = {
  alice: 10,
  bob: 20
};
```

### Partial

Makes all properties optional.

```ts
type User = {
  name: string;
  age: number;
};

const update: Partial<User> = {
  age: 16
};
```

### Pick

Selects specific properties.

```ts
type UserName = Pick<User, "name">;
```

### Omit

Removes specific properties.

```ts
type UserWithoutAge = Omit<User, "age">;
```

---

## 🔑 Quick Summary

| Generic | Purpose |
|---|---|
| `Array<T>` | Array of `T` |
| `Set<T>` | Unique values of `T` |
| `Map<K, V>` | Key-value pairs |
| `Promise<T>` | Future value of `T` |
| `Readonly<T>` | Makes properties readonly |
| `ReadonlyArray<T>` | Readonly array |
| `Record<K, V>` | Object with key/value types |
| `Partial<T>` | Makes all properties optional |
| `Pick<T, K>` | Selects specific properties |
| `Omit<T, K>` | Removes specific properties |

### Important

```ts
string[] === Array<string>
```

Both represent an array containing strings.

### Common Mistakes

```ts
new Sets<string>()     // ❌
new Set<string>()      // ✅

set.set("Hi")          // ❌
set.add("Hi")          // ✅
```
