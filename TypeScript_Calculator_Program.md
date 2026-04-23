# 📘 TypeScript Calculator Program

## 🎯 Objective

Create a simple **Calculator using TypeScript** that performs:

* Addition
* Subtraction
* Multiplication
* Division

---

## 📁 File Name

```bash
calculator.ts
```

---

## 🧾 Code (`calculator.ts`)

```typescript
class Calculator {

    add(a: number, b: number): number {
        return a + b;
    }

    subtract(a: number, b: number): number {
        return a - b;
    }

    multiply(a: number, b: number): number {
        return a * b;
    }

    divide(a: number, b: number): number {
        if (b === 0) {
            console.log("Cannot divide by zero");
            return 0;
        }
        return a / b;
    }
}

// Object creation
let calc = new Calculator();

console.log("Addition:", calc.add(10, 5));
console.log("Subtraction:", calc.subtract(10, 5));
console.log("Multiplication:", calc.multiply(10, 5));
console.log("Division:", calc.divide(10, 5));
```

---

## ⚙️ How to Run the Program

### 🔹 Step 1: Install TypeScript

```bash
npm install -g typescript
```

---

### 🔹 Step 2: Compile the File

```bash
tsc calculator.ts
```

👉 This generates:

```bash
calculator.js
```

---

### 🔹 Step 3: Run the Program

```bash
node calculator.js
```

---

## ⚡ Alternative (Direct Run)

```bash
npm install -g ts-node
ts-node calculator.ts
```

---

## 🔄 Output

```text
Addition: 15
Subtraction: 5
Multiplication: 50
Division: 2
```

---

## 💡 Key Concepts (Viva Ready)

* TypeScript uses **classes and methods**
* Supports **OOP concepts**
* `number` type ensures type safety
* Prevents errors like division by zero

---

## 🚀 Future Improvements

* Take user input (CLI or UI)
* Add advanced operations (power, square root)
* Build calculator UI using HTML + TypeScript

---

## ✅ Conclusion

This program demonstrates how TypeScript can be used to build a simple calculator using object-oriented programming concepts.

---
