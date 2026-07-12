# JavaScript Basics

## Variable (`var`)

- **Function-scoped** (not block-scoped)
- Can be **redeclared** and **updated**
- Hoisted to the top of its scope (initialized as `undefined`)
- Avoid using in modern JS — prefer `let` / `const`

```js
var name = 'Kiran';
var name = 'John'; // redeclaration allowed
```

---

## Identifier

- **Name** given to variables, functions, classes, etc.
- Rules:
  - Can contain letters, digits, `_`, `$`
  - **Cannot start with a digit**
  - Case-sensitive (`age` !== `Age`)
  - Cannot be a reserved keyword (`if`, `for`, `class`, etc.)

```js
let firstName = 'Kiran';  // valid
let 1stName = 'Kiran';    // invalid
```

---

## Literal

A **fixed value** written directly in the source code.

| Type      | Example              |
|-----------|----------------------|
| String    | `"Hello"`, `'World'` |
| Number    | `42`, `3.14`         |
| Boolean   | `true`, `false`      |
| Object    | `{ name: 'Kiran' }`  |
| Array     | `[1, 2, 3]`          |
| Null      | `null`               |
| Undefined | `undefined`          |

```js
let age = 25;           // 25  → number literal
let greeting = 'Hi';    // 'Hi' → string literal
```

---

## Constant (`const`)

- **Block-scoped** (like `let`)
- **Cannot be redeclared** or **reassigned**
- Must be initialized at declaration
- For objects/arrays, the **reference** is fixed — contents can still change

```js
const pi = 3.14;
pi = 3.15;  // ❌ Error

const person = { name: 'Kiran' };
person.name = 'John';   // ✅ allowed (mutating, not reassigning)
```
