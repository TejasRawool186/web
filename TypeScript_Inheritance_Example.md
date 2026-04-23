# 📘 TypeScript Inheritance Example

## 🎯 Objective

Demonstrate **Inheritance in TypeScript**, where one class (child) inherits properties and methods from another class (parent).

---

## 📁 File Name

```bash id="k7o2u1"
inheritance.ts
```

---

## 🧾 Code (`inheritance.ts`)

```typescript id="9fd3la"
// Parent Class
class Person {
    name: string;

    constructor(name: string) {
        this.name = name;
    }

    display() {
        console.log("Name:", this.name);
    }
}

// Child Class (inherits Person)
class Student extends Person {
    course: string;

    constructor(name: string, course: string) {
        super(name); // call parent constructor
        this.course = course;
    }

    showDetails() {
        console.log("Course:", this.course);
    }
}

// Object creation
let s1 = new Student("Tejas", "IT");

s1.display();      // inherited method
s1.showDetails();  // child method
```

---

## ⚙️ How to Run the File

### 🔹 Step 1: Install TypeScript

```bash id="d0y4kx"
npm install -g typescript
```

---

### 🔹 Step 2: Compile the File

```bash id="3lfxqk"
tsc inheritance.ts
```

👉 This will generate:

```bash id="6y3q2v"
inheritance.js
```

---

### 🔹 Step 3: Run the File

```bash id="7x4l2p"
node inheritance.js
```

---

## ⚡ Alternative (Direct Run)

```bash id="o0nlk3"
npm install -g ts-node
ts-node inheritance.ts
```

---

## 🔄 Output

```text id="4bdk19"
Name: Tejas
Course: IT
```

---

## 💡 Explanation

* `Person` → Parent class
* `Student` → Child class
* `extends` → used for inheritance
* `super()` → calls parent constructor
* Child class can use both **parent + own methods**

---

## 🧪 Key Points (Viva Ready)

* Inheritance promotes **code reuse**
* Use `extends` keyword
* `super()` is mandatory in child constructor
* Supports **OOP concepts**

---

## 🚀 Real-Life Example

* Parent: `Vehicle`
* Child: `Car`, `Bike`
* Common properties reused

---

## ✅ Conclusion

Inheritance in TypeScript allows one class to reuse and extend another class’s functionality, making code more modular and efficient.

---
