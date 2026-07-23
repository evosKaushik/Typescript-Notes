# 📝 Union & Intersection in Property-Based Sets

## 🌍 Universal Set

```text
U = All learners enrolled in the TypeScript course
```

Each learner has properties:

- Name
- Age
- City
- Qualification
- Occupation

> A **property-based set** is created by applying conditions (filters) on these properties.

---

## 🔵 Set A

Conditions:

- Age = 20
- City = Delhi
- Qualification = B.Tech

```text
A = {
  learners :
  age = 20 AND
  city = Delhi AND
  qualification = B.Tech
}
```

---

## 🟢 Set B

Conditions:

- Occupation = Student
- City = Delhi
- Qualification = BCA

```text
B = {
  learners :
  occupation = student AND
  city = Delhi AND
  qualification = BCA
}
```

---

# 🔗 Union (`A ∪ B`)

**Meaning**

- Learners satisfying **A OR B**.

✔ Can belong to:

- A
- B
- Both

### What is Guaranteed?

| Property | Guaranteed? |
|----------|-------------|
| City = Delhi | ✅ |
| Age = 20 | ❌ |
| Occupation = Student | ❌ |
| Qualification | ❌ |

### 💡 Key Insight

- Union → **Bigger set**
- Bigger set → **Fewer guarantees**

> **Rule:** Union guarantees **only the properties common to both sets**.

---

# 🎯 Intersection (`A ∩ B`)

**Meaning**

- Learners satisfying **A AND B**.

### Combine Conditions

From **A**

- Age = 20
- City = Delhi
- Qualification = B.Tech

From **B**

- Occupation = Student
- City = Delhi
- Qualification = BCA

### ⚠️ Conflict

```text
Qualification = B.Tech
Qualification = BCA
```

A learner cannot satisfy both.

```text
A ∩ B = ∅
```

---

## ✅ Fixed Example

If **Set B** becomes:

- Occupation = Student
- City = Delhi
- Qualification = B.Tech

Then:

```text
A ∩ B = {
  learners :
  age = 20 AND
  occupation = student AND
  city = Delhi AND
  qualification = B.Tech
}
```

### What is Guaranteed?

| Property | Guaranteed? |
|----------|-------------|
| Age = 20 | ✅ |
| Occupation = Student | ✅ |
| City = Delhi | ✅ |
| Qualification = B.Tech | ✅ |

### 💡 Key Insight

- Intersection → **Smaller set**
- Smaller set → **More guarantees**

---

# ⭐ Golden Rules

- **Union of Sets** → **Intersection of Guarantees**
- **Intersection of Sets** → **Union of Guarantees**

---

# 🧠 Intuition

### 🔗 Union (`A ∪ B`)

```text
Bigger Group
     ↓
Mixed Learners
     ↓
Less Certainty
     ↓
Only Common Guarantees
```

### 🎯 Intersection (`A ∩ B`)

```text
Smaller Group
     ↓
Strict Filtering
     ↓
More Certainty
     ↓
More Guarantees
```

---

# 📌 Final Takeaway

- **More values allowed (Union)** → **Fewer guarantees**
- **Fewer values allowed (Intersection)** → **More guarantees**