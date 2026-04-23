# 📘 AngularJS Event Handling

## 🎯 Objective

Understand how to handle **user events** in AngularJS using built-in directives like:

* `ng-click`
* `ng-change`
* `ng-mouseover`
* `ng-keyup`

---

## 🛠️ Technologies Used

* HTML
* JavaScript
* AngularJS (1.x)

---

## 📁 Project Structure

```bash
project/
 └── index.html
```

---

## 🌐 Example Code (`index.html`)

```html
<!DOCTYPE html>
<html ng-app="eventApp">
<head>
    <title>AngularJS Event Handling</title>

    <!-- AngularJS CDN -->
    <script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.8.2/angular.min.js"></script>

    <style>
        body { font-family: Arial; margin: 20px; }
        button, input { margin: 10px; padding: 5px; }
    </style>
</head>

<body ng-controller="EventController">

<h2>📘 AngularJS Event Handling Demo</h2>

<!-- ng-click -->
<button ng-click="showMessage()">Click Me</button>
<p>{{message}}</p>

<!-- ng-change -->
<input type="text" ng-model="name" ng-change="updateName()" placeholder="Enter your name">
<p>{{nameMessage}}</p>

<!-- ng-mouseover -->
<p ng-mouseover="hoverMessage='Mouse is over text!'">
    Hover over this text
</p>
<p>{{hoverMessage}}</p>

<!-- ng-keyup -->
<input type="text" ng-model="keyInput" ng-keyup="keyPress()"
       placeholder="Type something">
<p>{{keyMessage}}</p>

<script>
var app = angular.module("eventApp", []);

app.controller("EventController", function($scope) {

    // Click event
    $scope.showMessage = function() {
        $scope.message = "Button Clicked!";
    };

    // Change event
    $scope.updateName = function() {
        $scope.nameMessage = "Hello " + $scope.name;
    };

    // Keyup event
    $scope.keyPress = function() {
        $scope.keyMessage = "You typed: " + $scope.keyInput;
    };

});
</script>

</body>
</html>
```

---

## ▶️ How to Run

1. Create `index.html`
2. Paste the above code
3. Open in browser

---

## 🔄 Working Flow

* User interacts with UI elements
* AngularJS detects events using directives
* Functions in controller are triggered
* UI updates automatically via data binding

---

## 💡 Common AngularJS Events

| Directive      | Description                        |
| -------------- | ---------------------------------- |
| `ng-click`     | Triggered when button is clicked   |
| `ng-change`    | Triggered when input value changes |
| `ng-mouseover` | Triggered when mouse hovers        |
| `ng-keyup`     | Triggered when key is released     |

---

## 💡 Viva Points

* AngularJS uses **event directives** instead of traditional JS event listeners
* Provides **two-way data binding**
* Reduces manual DOM manipulation
* Improves code readability

---

## 🚀 Future Improvements

* Add form validation using events
* Combine multiple events in one app
* Integrate with backend

---

## ✅ Conclusion

AngularJS event handling simplifies user interaction by directly binding events to functions, making web applications more dynamic and interactive.

---
