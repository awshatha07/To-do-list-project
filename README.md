# To-do-list-project
TO-DO LIST documentation and files
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>To Do List App</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <div class="container">
        <h2>To Do List App</h2>

        <input type="text" id="taskInput" placeholder="Enter your task">
        <button onclick="addTask()">Add Task</button>

        <ul id="taskList"></ul>
    </div>

    <script src="script.js"></script>
</body>
</html>
body {
    font-family: Arial, sans-serif;
    background-color: #f2f2f2;
    display: flex;
    justify-content: center;
    margin-top: 50px;
}

.container {
    background-color: white;
    padding: 20px;
    width: 300px;
    text-align: center;
    border-radius: 5px;
}

input {
    width: 80%;
    padding: 8px;
}

button {
    padding: 8px;
    margin-top: 10px;
}

ul {
    list-style: none;
    padding: 0;
}

li {
    background: #eee;
    padding: 8px;
    margin-top: 10px;
    display: flex;
    justify-content: space-between;
}

.completed {
    text-decoration: line-through;
    color: gray;
}
function addTask() {
    let input = document.getElementById("taskInput");
    let taskText = input.value;

    if (taskText === "") {
        alert("Please enter a task");
        return;
    }

    let li = document.createElement("li");

    let span = document.createElement("span");
    span.textContent = taskText;

    span.onclick = function () {
        span.classList.toggle("completed");
    };

    let deleteBtn = document.createElement("button");
    deleteBtn.textContent = "Delete";
    deleteBtn.onclick = function () {
        li.remove();
    };

    li.appendChild(span);
    li.appendChild(deleteBtn);

    document.getElementById("taskList").appendChild(li);
    input.value = "";
}
