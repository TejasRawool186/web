# 📘 AngularJS Student Record Application

## 🎯 Objective

Build a simple **Student Record Management System** using AngularJS that allows users to:

* Add student details
* View student records
* Delete student entries

---

## 🛠️ Technologies Used

* HTML
* CSS
* JavaScript
* AngularJS (1.x)

---

## 📁 Project Structure

```bash
project/
 └── index.html
```

---

## 🌐 Application Code (`index.html`)

```html
<!DOCTYPE html>
<html ng-app="studentApp">
<head>
    <title>Student Record - AngularJS</title>

    <!-- AngularJS CDN -->
    <script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.8.2/angular.min.js"></script>

    <style>
        body { font-family: Arial; margin: 20px; }
        input { margin: 5px; padding: 5px; }
        button { margin: 5px; padding: 5px; }
        table { border-collapse: collapse; width: 60%; margin-top: 20px; }
        table, th, td { border: 1px solid black; padding: 8px; text-align: center; }
    </style>
</head>

<body ng-controller="StudentController">

<h2>📘 Student Record System</h2>

<!-- Form -->
<input type="text" ng-model="student.name" placeholder="Enter Name" required>
<input type="number" ng-model="student.age" placeholder="Enter Age" required>
<input type="text" ng-model="student.course" placeholder="Enter Course" required>

<button ng-click="addStudent()">Add Student</button>

<!-- Table -->
<table>
    <tr>
        <th>Name</th>
        <th>Age</th>
        <th>Course</th>
        <th>Action</th>
    </tr>

    <tr ng-repeat="s in students">
        <td>{{s.name}}</td>
        <td>{{s.age}}</td>
        <td>{{s.course}}</td>
        <td>
            <button ng-click="deleteStudent($index)">Delete</button>
        </td>
    </tr>
</table>

<script>
var app = angular.module("studentApp", []);

app.controller("StudentController", function($scope) {

    // Student list
    $scope.students = [];

    // Add student
    $scope.addStudent = function() {
        if ($scope.student.name && $scope.student.age && $scope.student.course) {
            $scope.students.push({
                name: $scope.student.name,
                age: $scope.student.age,
                course: $scope.student.course
            });

            // Clear form
            $scope.student = {};
        } else {
            alert("Please fill all fields!");
        }
    };

    // Delete student
    $scope.deleteStudent = function(index) {
        $scope.students.splice(index, 1);
    };

});
</script>

</body>
</html>
```

---

## ▶️ How to Run the Project

1. Create a file named `index.html`
2. Copy and paste the above code
3. Open the file in any web browser

---

## 🔄 Working Flow

1. User enters student details (Name, Age, Course)
2. Clicks **Add Student**
3. Data is stored in an array (`$scope.students`)
4. Table updates dynamically using `ng-repeat`
5. User can delete records

---

## 💡 Key Concepts (Viva Ready)

* **AngularJS**: JavaScript framework for dynamic web apps
* `ng-app`: Initializes AngularJS app
* `ng-controller`: Controls application logic
* `ng-model`: Two-way data binding
* `ng-repeat`: Displays list data
* `$scope`: Connects data between UI and controller

---

## 🚀 Future Improvements

* Edit student details
* Add search and filter functionality
* Store data in Local Storage
* Connect to backend (Node.js + MongoDB)

---

## ✅ Conclusion

This application demonstrates how AngularJS enables dynamic data binding and real-time UI updates for managing student records efficiently.

---
