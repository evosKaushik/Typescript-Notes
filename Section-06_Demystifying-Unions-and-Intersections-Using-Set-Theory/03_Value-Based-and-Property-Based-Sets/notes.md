# 📝 Value-Based and Property-Based Sets

## 🔢 Value-Based Sets

**Meaning**

- Membership is decided by the **value itself**.

**Condition**

```text
x > 0
x % 2 = 0
```

**Examples**

```text
A = {x : x % 2 = 0}
```

```text
A = {..., -4, -2, 0, 2, 4, ...}
```

```text
B = {x : x < 5 and x ∈ N}
```

```text
B = {1, 2, 3, 4}
```

```text
C = {a, b, c}
```

**Characteristics**

- Primitive values
  - Numbers
  - Characters
  - Symbols

---

## 🧩 Property-Based Sets

**Meaning**

- Membership is decided using the **properties of an object**.

**Condition**

```text
m.color = "yellow"
s.marks > 90
p.price < 1000
```

**Examples**

```text
M = {m : m is a mango and m.color = "yellow"}
```

```text
S = {s : s.marks > 90}
```

```text
P = {p : p.price < 1000}
```

**Characteristics**

- Elements are objects.
- Objects have properties such as:
  - Color
  - Size
  - Price
  - Marks

---

## 💡 Key Difference

| Value-Based | Property-Based |
|-------------|----------------|
| Condition on the value | Condition on object properties |
| Uses primitive values | Uses objects |

> **Common Idea:** A set contains all elements that satisfy a given condition.

---

# 📝 Multiple Property-Based Sets

Assume each **person** has these properties:

- Name
- Age
- Height
- City

---

## 1️⃣ One Property

```text
P₁ = {p : p.age > 18}
```

✔ People older than 18.

---

## 2️⃣ Two Properties

```text
P₂ = {p : p.age > 18 and p.height > 170}
```

✔ People who:

- Age > 18
- Height > 170 cm

---

## 3️⃣ Three Properties

```text
P₃ = {p : p.age > 18 and p.height > 170 and p.city = "Delhi"}
```

✔ People who:

- Age > 18
- Height > 170 cm
- City = Delhi

---

## 🎯 Key Insight

Each new property acts as a **filter**.

```text
All People
      ↓
Age > 18
      ↓
Height > 170
      ↓
City = Delhi
      ↓
Smaller Set
```

> **Rule:** The more conditions (properties) you add, the **smaller** and more **filtered** the resulting set becomes.