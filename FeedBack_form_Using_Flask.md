# 📘 Feedback Form using Flask

## 🎯 Objective

Design a **Feedback Form web application using Flask** that:

* Takes user input (name, email, feedback)
* Submits data to backend
* Displays a success message

---

## 🛠️ Technologies Used

* Python (Flask)
* HTML
* CSS (optional)

---

## 📁 Project Structure

```bash
project/
 ├── app.py
 └── templates/
      ├── index.html
      └── success.html
```

---

## 🧾 1. Backend Code (`app.py`)

```python
from flask import Flask, render_template, request

app = Flask(__name__)

@app.route("/")
def home():
    return render_template("index.html")

@app.route("/submit", methods=["POST"])
def submit():
    name = request.form["name"]
    email = request.form["email"]
    feedback = request.form["feedback"]

    # You can store data in database/file here
    print(name, email, feedback)

    return render_template("success.html", name=name)

if __name__ == "__main__":
    app.run(debug=True)
```

---

## 🌐 2. Frontend (`templates/index.html`)

```html
<!DOCTYPE html>
<html>
<head>
    <title>Feedback Form</title>
</head>
<body>

<h2>📘 Feedback Form</h2>

<form action="/submit" method="POST">
    <input type="text" name="name" placeholder="Enter Name" required><br><br>
    <input type="email" name="email" placeholder="Enter Email" required><br><br>
    
    <textarea name="feedback" placeholder="Enter Feedback" required></textarea><br><br>
    
    <button type="submit">Submit</button>
</form>

</body>
</html>
```

---

## 🎉 3. Success Page (`templates/success.html`)

```html
<!DOCTYPE html>
<html>
<head>
    <title>Success</title>
</head>
<body>

<h2>✅ Thank You {{name}}!</h2>
<p>Your feedback has been submitted successfully.</p>

<a href="/">Go Back</a>

</body>
</html>
```

---

## ▶️ How to Run the Project

### 🔹 Step 1: Install Flask

```bash
pip install flask
```

---

### 🔹 Step 2: Run the Application

```bash
python app.py
```

---

### 🔹 Step 3: Open Browser

```
http://127.0.0.1:5000/
```

---

## 🔄 Working Flow

1. User opens feedback form
2. Enters name, email, feedback
3. Clicks submit
4. Data is sent to Flask backend
5. Backend processes data
6. Success page is displayed

---

## 💡 Key Concepts (Viva Ready)

* Flask is a **micro web framework**
* `render_template()` → loads HTML files
* `request.form` → gets form data
* `POST` method → used for submitting data

---

## 🚀 Future Improvements

* Store feedback in database (SQLite/MySQL)
* Add validation & error handling
* Add CSS styling (Bootstrap)
* Display all feedback entries

---

## ✅ Conclusion

This project demonstrates how to build a simple web form using Flask and handle user input efficiently.

---
Fe
