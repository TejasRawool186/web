# 📘 TypeScript Access Modifiers (With Execution Guide)

## 🎯 Objective

Understand **Access Modifiers in TypeScript** and learn how to **run a `.ts` file**.

---

## 📁 File Name

```bash
student.ts
```

---

## 🧾 Code (`student.ts`)

```typescript
class Student {
    public name: string;
    private age: number;
    protected course: string;

    constructor(name: string, age: number, course: string) {
        this.name = name;
        this.age = age;
        this.course = course;
    }

    display() {
        console.log("Name:", this.name);
        console.log("Age:", this.age);
        console.log("Course:", this.course);
    }
}

class ChildStudent extends Student {
    showCourse() {
        console.log("Course:", this.course); // protected access
    }
}

let s1 = new Student("Tejas", 21, "IT");
s1.display();

console.log(s1.name);
// console.log(s1.age);      ❌ Error
// console.log(s1.course);   ❌ Error
```

---

## ⚙️ How to Run the File

### 🔹 Step 1: Install TypeScript

```bash
npm install -g typescript
```

---

### 🔹 Step 2: Compile TypeScript to JavaScript

```bash
tsc student.ts
```

👉 This will generate:

```bash
student.js
```

---

### 🔹 Step 3: Run the JavaScript File

```bash
node student.js
```

---

## ⚡ Alternative (Run Without Compiling)

### Install `ts-node`

```bash
npm install -g ts-node
```

### Run directly

```bash
ts-node student.ts
```

---

## 🔄 Output

```text
Name: Tejas
Age: 21
Course: IT
Tejas
```

---

## 💡 Key Points (Viva Ready)

* `.ts` → TypeScript file
* `tsc` → TypeScript compiler
* `.js` → Executable JavaScript file
* `public` → accessible everywhere
* `private` → only inside class
* `protected` → accessible in subclass

---

## ✅ Conclusion

TypeScript files (`.ts`) must be compiled into JavaScript before execution. Access modifiers help in controlling data visibility and improving code security.

---
