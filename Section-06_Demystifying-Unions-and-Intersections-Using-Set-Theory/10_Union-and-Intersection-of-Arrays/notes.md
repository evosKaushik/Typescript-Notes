# 📝 Union and Intersection of Arrays

```ts
type T1 = number[];
type T2 = string[];
```

## 🔀 Union of Arrays `|`

```ts
const arr: T1 | T2 = [1, 2, 3];
```

The array must be **either** a `number[]` OR a `string[]`.

```ts
const arr1: T1 | T2 = [1, 2, 3];       // ✅
const arr2: T1 | T2 = ["a", "b", "c"];  // ✅
const arr3: T1 | T2 = [1, "hello"];     // ❌
```

> `T1 | T2` = either a complete `number[]` OR a complete `string[]`.

---

## 🤝 Intersection of Arrays `&`

```ts
const arr: T1 & T2 = [1, 2, 3];
```

The array must satisfy **both**:

```text
number[] AND string[]
```

Each element would need to be both a `number` and a `string`.

```text
number & string → never
```

So conceptually:

```ts
type T = never[];
```

An empty array is valid because it has no element that conflicts:

```ts
const arr: T1 & T2 = []; // ✅
```

But:

```ts
const arr: T1 & T2 = [1, 2, 3]; // ❌
```

---

## 🔄 If We Want Both Number and String

Use a **union inside the array**:

```ts
const arr: (number | string)[] = [1, "hello", 2, "world"];
```

Here each element can be:

```text
number OR string
```

### 🧠 Remember

```text
number[] | string[]
→ either a number array OR a string array

number[] & string[]
→ never[] (elements must be both)

(number | string)[]
→ one array containing numbers and strings
```
