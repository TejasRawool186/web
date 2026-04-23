# 📘 RESTful API using MongoDB

## 🎯 Objective

Build a **RESTful API** using:

* Node.js
* Express.js
* MongoDB (Mongoose)

The API will perform **CRUD operations** (Create, Read, Update, Delete).

---

## 🛠️ Technologies Used

* Node.js
* Express.js
* MongoDB
* Mongoose

---

## 📁 Project Structure

```bash id="7l6sht"
project/
 ├── server.js
 ├── models/
 │     └── User.js
 └── routes/
       └── userRoutes.js
```

---

## ⚙️ Step 1: Initialize Project

```bash id="rmp4zb"
npm init -y
npm install express mongoose cors
```

---

## 🧾 1. Server File (`server.js`)

```javascript id="dv9l8m"
const express = require("express");
const mongoose = require("mongoose");
const cors = require("cors");

const app = express();

app.use(cors());
app.use(express.json());

// MongoDB connection
mongoose.connect("mongodb://127.0.0.1:27017/testdb")
    .then(() => console.log("MongoDB Connected"))
    .catch(err => console.log(err));

// Routes
const userRoutes = require("./routes/userRoutes");
app.use("/api/users", userRoutes);

app.get("/", (req, res) => {
    res.send("API Running...");
});

app.listen(5000, () => {
    console.log("Server running on port 5000");
});
```

---

## 📦 2. Model (`models/User.js`)

```javascript id="uqjv86"
const mongoose = require("mongoose");

const userSchema = new mongoose.Schema({
    name: String,
    email: String
});

module.exports = mongoose.model("User", userSchema);
```

---

## 🌐 3. Routes (`routes/userRoutes.js`)

```javascript id="88ctqq"
const express = require("express");
const router = express.Router();
const User = require("../models/User");

// CREATE
router.post("/", async (req, res) => {
    const user = new User(req.body);
    const saved = await user.save();
    res.json(saved);
});

// READ ALL
router.get("/", async (req, res) => {
    const users = await User.find();
    res.json(users);
});

// READ ONE
router.get("/:id", async (req, res) => {
    const user = await User.findById(req.params.id);
    res.json(user);
});

// UPDATE
router.put("/:id", async (req, res) => {
    const user = await User.findByIdAndUpdate(req.params.id, req.body, { new: true });
    res.json(user);
});

// DELETE
router.delete("/:id", async (req, res) => {
    await User.findByIdAndDelete(req.params.id);
    res.json({ message: "User deleted" });
});

module.exports = router;
```

---

## ▶️ How to Run the Project

### 🔹 Step 1: Start MongoDB

```bash id="6h3gxz"
mongod
```

---

### 🔹 Step 2: Run Server

```bash id="9pnrkn"
node server.js
```

---

### 🔹 Step 3: Test API

Use:

* Postman
* Browser
* Thunder Client

---

## 📌 API Endpoints

| Method | Endpoint         | Description     |
| ------ | ---------------- | --------------- |
| GET    | `/api/users`     | Get all users   |
| GET    | `/api/users/:id` | Get single user |
| POST   | `/api/users`     | Create user     |
| PUT    | `/api/users/:id` | Update user     |
| DELETE | `/api/users/:id` | Delete user     |

---

## 🔄 Example JSON (POST)

```json id="8nm9sj"
{
  "name": "Tejas",
  "email": "tejas@gmail.com"
}
```

---

## 💡 Key Concepts (Viva Ready)

* REST API → Uses HTTP methods (GET, POST, PUT, DELETE)
* MongoDB → NoSQL database
* Mongoose → ODM for MongoDB
* Express → Handles routing

---

## 🚀 Future Improvements

* Add validation (Joi/Zod)
* Add authentication (JWT)
* Use MVC structure
* Deploy on cloud (Render/Heroku)

---

## ✅ Conclusion

This project demonstrates how to build a RESTful API with MongoDB and perform CRUD operations efficiently.

---
