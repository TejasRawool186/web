# 📘 AJAX JavaScript Demo

## 🎯 Objective

This project demonstrates how to use **AJAX (Asynchronous JavaScript and XML)** to load data from a server/file and display it on a web page **without reloading**.

---

## 🛠️ Technologies Used

* HTML
* JavaScript
* AJAX (`XMLHttpRequest` & Fetch API)

---

## 📁 Project Structure

```bash
project/
 ├── index.html
 └── data.txt
```

---

## 🌐 1. Frontend Code (`index.html`)

```html
<!DOCTYPE html>
<html>
<head>
    <title>AJAX Example</title>
</head>
<body>

<h2>AJAX Demo</h2>

<button onclick="loadData()">Get Data</button>

<p id="result"></p>

<script>
function loadData() {
    var xhr = new XMLHttpRequest();

    xhr.open("GET", "data.txt", true);

    xhr.onreadystatechange = function() {
        if (xhr.readyState === 4 && xhr.status === 200) {
            document.getElementById("result").innerHTML = xhr.responseText;
        }
    };

    xhr.send();
}
</script>

</body>
</html>
```

---

## 📄 2. Data File (`data.txt`)

```text
Hello Tejas! This data is loaded using AJAX.
```

---

## ▶️ How to Run the Project

### Step 1: Create Files

* Create a folder named `project`
* Add `index.html` and `data.txt`

### Step 2: Run Using Browser

* Open `index.html` in your browser
  *(Recommended: Use Live Server in VS Code for best results)*

---

## 🔄 Working Flow

1. User clicks **Get Data button**
2. AJAX request is created using `XMLHttpRequest`
3. Request is sent to `data.txt`
4. Response is received
5. Data is displayed on the same page

---

## 💡 Key Concepts (Viva Ready)

* **AJAX**: Loads data asynchronously without refreshing page
* **XMLHttpRequest**: Traditional AJAX method
* **Fetch API**: Modern alternative for AJAX
* **readyState = 4** → Request complete
* **status = 200** → Successful response

---

## ⚡ Bonus: Fetch API Version

```javascript
function loadData() {
    fetch("data.txt")
        .then(response => response.text())
        .then(data => {
            document.getElementById("result").innerHTML = data;
        });
}
```

---

## 🚀 Future Improvements

* Connect to backend (Node.js / PHP / MongoDB)
* Add form validation using AJAX
* Use JSON data instead of text file
* Add loading spinner

---

## ✅ Conclusion

This project shows how AJAX improves user experience by dynamically loading data without refreshing the page.

---
