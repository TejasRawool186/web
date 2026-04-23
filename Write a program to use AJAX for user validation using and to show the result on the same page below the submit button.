# 📘 AJAX User Validation (Single Page Result Display)

## 🎯 Objective

Build a simple web application that uses **AJAX** to validate a user (username) and display the result **on the same page below the submit button** without reloading.

---

## 🛠️ Technologies Used

* HTML
* JavaScript (Fetch API for AJAX)
* Node.js
* Express.js

---

## 📁 Project Structure

```
project/
 ├── server.js
 └── index.html
```

---

## 🌐 1. Frontend Code (`index.html`)

```html
<!DOCTYPE html>
<html>
<head>
    <title>AJAX User Validation</title>
</head>
<body>

<h2>User Validation Form</h2>

<form id="userForm">
    <input type="text" id="username" placeholder="Enter Username" required>
    <button type="submit">Validate</button>
</form>

<p id="result"></p>

<script>
document.getElementById("userForm").addEventListener("submit", function(e) {
    e.preventDefault();

    let username = document.getElementById("username").value;

    // AJAX request using Fetch API
    fetch("http://localhost:5000/validate-user", {
        method: "POST",
        headers: {
            "Content-Type": "application/json"
        },
        body: JSON.stringify({ username: username })
    })
    .then(response => response.json())
    .then(data => {
        document.getElementById("result").innerText = data.message;
    })
    .catch(error => console.error(error));
});
</script>

</body>
</html>
```

---

## ⚙️ 2. Backend Code (`server.js`)

```javascript
const express = require("express");
const cors = require("cors");

const app = express();

app.use(cors());
app.use(express.json());

// Dummy user list (simulate database)
const users = ["tejas", "admin", "user123"];

// API endpoint for validation
app.post("/validate-user", (req, res) => {
    const { username } = req.body;

    if (users.includes(username.toLowerCase())) {
        res.json({ message: "✅ User already exists" });
    } else {
        res.json({ message: "❌ User not found / available" });
    }
});

app.listen(5000, () => {
    console.log("Server running on port 5000");
});
```

---

## ▶️ How to Run the Project

### Step 1: Initialize Project

```bash
npm init -y
```

### Step 2: Install Dependencies

```bash
npm install express cors
```

### Step 3: Run Server

```bash
node server.js
```

### Step 4: Open Frontend

* Open `index.html` in your browser

---

## 🔄 Working Flow

1. User enters a username
2. Clicks **Validate button**
3. AJAX request is sent to the server
4. Server checks username in the list
5. Response is returned
6. Result is displayed **below the button without page reload**

---

## 🧪 Example Output

| Input   | Output                |
| ------- | --------------------- |
| tejas   | ✅ User already exists |
| newuser | ❌ User not found      |

---

## 💡 Key Concepts (Viva Ready)

* **AJAX**: Asynchronous communication without page reload
* **Fetch API**: Modern way to send HTTP requests
* **Express.js**: Backend framework for APIs
* **JSON**: Data format used for communication

---

## 🚀 Future Improvements

* Connect to real database (MongoDB/MySQL)
* Add email/password validation
* Show loading spinner during request
* Use React/Frontend frameworks

---

## ✅ Conclusion

This project demonstrates how AJAX improves user experience by enabling real-time validation without refreshing the page.

---
