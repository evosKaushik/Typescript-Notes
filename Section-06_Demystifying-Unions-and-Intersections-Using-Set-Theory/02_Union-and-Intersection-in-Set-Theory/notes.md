# 📝 Set Operations (Mind Map)

## 🔗 Union (`A ∪ B`)

**Meaning**

- All elements in **A** or **B** (or both).

**Example**

```text
A = {1, 2, 3}
B = {3, 4, 5}

A ∪ B = {1, 2, 3, 4, 5}
```

**Remember**

- No duplicate elements.
- Order doesn't matter.
- Union always produces a new set.

**Set-Builder Form**

```text
A ∪ B = {x : x ∈ A or x ∈ B}
```

**Venn Diagram**

- Shade **all of A and B**.

---

## 🎯 Intersection (`A ∩ B`)

**Meaning**

- Elements common to both **A** and **B**.

**Example**

```text
A = {1, 2, 3}
B = {2, 3, 4}

A ∩ B = {2, 3}
```

**Set-Builder Form**

```text
A ∩ B = {x : x ∈ A and x ∈ B}
```

**Venn Diagram**

- Shade **only the overlapping region**.

---

## ➖ Difference (`A - B` or `A \ B`)

**Meaning**

- Elements in **A** but **not** in **B**.

**Example**

```text
A = {1, 2, 3}
B = {2, 3, 4}

A - B = {1}
```

**Set-Builder Form**

```text
A - B = {x : x ∈ A and x ∉ B}
```

**Venn Diagram**

- Shade **only the part of A outside B**.

---

## 📌 Key Points

- **Union (`∪`)** → All unique elements.
- **Intersection (`∩`)** → Common elements.
- **Difference (`-`)** → Elements in the first set only.

---

## ⚡ Important Properties

- **No duplicates**
  ```text
  A ∪ B → Unique elements only
  ```

- **Order doesn't matter**
  ```text
  {1,2,3} = {3,2,1}
  ```

- **Direction matters for difference**
  ```text
  A - B ≠ B - A
  ```

  Example:

  ```text
  A - B = {1}
  B - A = {4}
  ```