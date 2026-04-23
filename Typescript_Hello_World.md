# 📘 TypeScript Basic Programs (Small Code Snippets)

## 🎯 Objective

Learn basic TypeScript programs like **Hello World, variables, functions, and simple logic**.

---

## 📁 File Names

You can create separate files or use one file like:

```bash
hello.ts
variables.ts
functions.ts
```

---

## 🧾 1. Hello World (`hello.ts`)

```typescript
console.log("Hello, World!");
```

---

## 🧾 2. Variables & Data Types (`variables.ts`)

```typescript
let name: string = "Tejas";
let age: number = 21;
let isStudent: boolean = true;

console.log(name, age, isStudent);
```

---

## 🧾 3. Function Example (`functions.ts`)

```typescript
function add(a: number, b: number): number {
    return a + b;
}

console.log(add(5, 3));
```

---

## 🧾 4. Arrow Function

```typescript
const multiply = (x: number, y: number): number => x * y;

console.log(multiply(4, 5));
```

---

## 🧾 5. If-Else Example

```typescript
let num: number = 10;

if (num % 2 === 0) {
    console.log("Even number");
} else {
    console.log("Odd number");
}
```

---

## 🧾 6. Loop Example

```typescript
for (let i: number = 1; i <= 5; i++) {
    console.log(i);
}
```

---

## 🧾 7. Array Example

```typescript
let numbers: number[] = [1, 2, 3];

numbers.forEach(n => console.log(n));
```

---

## 🧾 8. Class Example

```typescript
class Student {
    name: string;

    constructor(name: string) {
        this.name = name;
    }

    greet() {
        console.log("Hello " + this.name);
    }
}

let s1 = new Student("Tejas");
s1.greet();
```

---

## ⚙️ How to Run TypeScript Files

### 🔹 Step 1: Install TypeScript

```bash
npm install -g typescript
```

---

### 🔹 Step 2: Compile File

```bash
tsc hello.ts
```

👉 This generates `hello.js`

---

### 🔹 Step 3: Run File

```bash
node hello.js
```

---

## ⚡ Alternative (Direct Run)

```bash
npm install -g ts-node
ts-node hello.ts
```

---

## 💡 Key Points (Viva Ready)

* `.ts` → TypeScript file
* `tsc` → TypeScript compiler
* TypeScript adds **types to JavaScript**
* Improves **code safety and readability**

---

## ✅ Conclusion

These small programs help in understanding the basics of TypeScript including variables, functions, loops, and classes.

---
