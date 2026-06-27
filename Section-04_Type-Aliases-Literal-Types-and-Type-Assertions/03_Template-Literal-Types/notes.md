# 🧩 Template Literal Types

> **Topic:** TypeScript (Template Literal Types)

---

# 🤔 What are Template Literal Types?

**Template Literal Types** allow you to create new string types by combining **literal types** using the same syntax as JavaScript template strings.

They let TypeScript verify that a string follows a **specific pattern**.

Think of them as **string templates for types**.

For example, instead of allowing **any string**, you can enforce a format like:

```
/api/user
/api/posts
/api/comments
```

and reject every other value.

---

# 🎯 Why do we use Template Literal Types?

Template literal types are useful when a string must follow a predictable format.

They help you:

* ✅ Restrict strings to a specific pattern.
* ✅ Catch invalid strings during development.
* ✅ Get autocomplete suggestions in your editor.
* ✅ Make APIs safer and easier to use.

---

# 📝 Basic Syntax

Template literal types use backticks (`` ` ``) just like JavaScript template strings.

```ts id="5e2vnm"
type Greeting = `Hello`;
```

Although this example is simple, template literal types become powerful when combined with unions.

---

# 🔗 Combining with Union Types

Suppose your application has only three valid API endpoints.

```ts id="kv1kr7"
type Endpoints =
  | "user"
  | "posts"
  | "comments";
```

Now you can create a template literal type.

```ts id="twxtta"
type ApiRoute = `/api/${Endpoints}`;
```

Usage:

```ts id="vdf6cf"
const api: ApiRoute = "/api/posts";
```

✅ Allowed

```ts id="sb7y6j"
"/api/user"
"/api/posts"
"/api/comments"
```

❌ Not Allowed

```ts id="9hm7m8"
"/api/login"
"/users"
"/post"
```

TypeScript provides autocomplete for all valid routes because it knows every possible value.

> ⚠️ **Note:** The route should start with `/api/`, not `api/`.

---

# 📝 Inline Template Literal Types

You don't have to create a separate union type first.

You can write everything inline.

```ts id="7ng8oe"
type ApiRoute =
  `/api/${"user" | "posts" | "comments"}`;
```

Usage:

```ts id="mqr1m6"
const api: ApiRoute = "/api/posts";
```

This produces exactly the same result as creating the union separately.

---

# 🧠 What happens behind the scenes?

Template literal types exist **only in TypeScript**.

Example:

```ts id="ckj8gk"
type ApiRoute = `/api/${"user" | "posts"}`;

const api: ApiRoute = "/api/posts";
```

Compiles to:

```js id="pjlwmv"
const api = "/api/posts";
```

All type information is removed because JavaScript has no concept of template literal types.

---

# 🚀 Production Perspective

Template literal types are widely used in production applications for:

* 🌐 API endpoint definitions
* 🛣️ Route names
* 🎨 CSS utility class names
* 🌍 Internationalization (i18n) keys
* 📦 Event names
* ⚛️ Component variants
* 🔑 Object key generation

Example:

```ts id="jlwmkx"
type Theme = "light" | "dark";

type ThemeClass = `theme-${Theme}`;
```

Allowed values:

```ts id="mjlwmn"
"theme-light"
"theme-dark"
```

This prevents accidental typos and keeps string-based APIs type-safe.

---

# 📚 Key Points

✅ Template literal types create new string types from existing literal types.

✅ They use the same syntax as JavaScript template strings (backticks).

✅ They work especially well with union types.

✅ TypeScript validates the string pattern at compile time.

✅ They provide excellent autocomplete and type safety.

✅ They are completely removed when TypeScript compiles to JavaScript.

---

# 🎯 Remember

> **Literal Type** → One fixed value (`"user"`)
> **Union Type** → Multiple allowed values (`"user" | "posts"`)
> **Template Literal Type** → A string pattern built from those values (`/api/${...}`)
