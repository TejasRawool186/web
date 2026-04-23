# 📘 AngularJS Hello World Application

## 🎯 Objective

Create a simple **Hello World application using AngularJS** and demonstrate:

* `ng-controller`
* `ng-model`
* AngularJS expressions (`{{ }}`)

---

## 🛠️ Technologies Used

* HTML
* JavaScript
* AngularJS (1.x)

---

## 📁 Project Structure

```bash id="y0c7lq"
project/
 └── index.html
```

---

## 🌐 Application Code (`index.html`)

```html id="4g0yfz"
<!DOCTYPE html>
<html ng-app="myApp">
<head>
    <title>AngularJS Hello World</title>

    <!-- AngularJS CDN -->
    <script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.8.2/angular.min.js"></script>
</head>

<body ng-controller="MyController">

<h2>📘 AngularJS Hello World</h2>

<!-- Input using ng-model -->
<input type="text" ng-model="name" placeholder="Enter your name">

<!-- Expression -->
<p>Hello {{name}}!</p>

<script>
// Create AngularJS App
var app = angular.module("myApp", []);

// Create Controller
app.controller("MyController", function($scope) {
    $scope.name = "Tejas";
});
</script>

</body>
</html>
```

---

## ▶️ How to Run the Project

1. Create a file named `index.html`
2. Copy and paste the above code
3. Open the file in any browser

---

## 🔄 Working Flow

1. AngularJS app is initialized using `ng-app`
2. Controller is attached using `ng-controller`
3. User enters name in input field
4. `ng-model` binds input to variable
5. Expression `{{name}}` updates output dynamically

---

## 💡 Key Concepts (Viva Ready)

* **`ng-app`** → Initializes AngularJS application
* **`ng-controller`** → Manages application logic
* **`ng-model`** → Two-way data binding
* **Expressions (`{{ }}`)** → Display dynamic data

---

## 🧪 Example Output

* Input: `Tejas` → Output: **Hello Tejas!**
* Input: `John` → Output: **Hello John!**

---

## 🚀 Future Improvements

* Add styling (CSS/Bootstrap)
* Add form validation
* Extend to full student management system

---

## ✅ Conclusion

This simple project demonstrates how AngularJS enables dynamic data binding and real-time UI updates using controllers, models, and expressions.

---
