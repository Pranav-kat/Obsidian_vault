# Obsidian_vault
My Personal notes vault integrated with Github

Automating the notes publishing from Obsidian Vault to my personal Github repo.

Initial Configuration:
- Install the Github Publisher plugin
- Add the github details like username, repository and personal access token
- Create the notes with key share = true in the frontmatter
- Open the command palette to upload the active file
- Voila!! Your notes have been pushed to your repo.

Pro Tip: Refer the notes on Obsidian for better UI experience

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>To-Do List</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="container">
        <h1>To-Do List</h1>
        <div class="input-container">
            <input type="text" id="new-task" placeholder="Add a new task">
            <select id="priority">
                <option value="low">Low</option>
                <option value="medium">Medium</option>
                <option value="high">High</option>
            </select>
            <button id="add-task">Add Task</button>
        </div>
        <ul id="task-list"></ul>
    </div>

    <script src="scripts.js"></script>
</body>
</html>

body {
    font-family: Arial, sans-serif;
    background-color: #f4f4f4;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    margin: 0;
}

.container {
    background: white;
    padding: 20px;
    border-radius: 5px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    width: 300px;
}

h1 {
    text-align: center;
}

.input-container {
    display: flex;
    justify-content: space-between;
    margin-bottom: 20px;
}

#new-task {
    flex: 2;
    padding: 5px;
}

#priority {
    flex: 1;
    padding: 5px;
    margin-left: 10px;
}

button {
    padding: 5px 10px;
    margin-left: 10px;
}

ul {
    list-style: none;
    padding: 0;
}

li {
    display: flex;
    justify-content: space-between;
    padding: 5px;
    border-bottom: 1px solid #ddd;
}

li.low {
    background-color: #e0f7fa;
}

li.medium {
    background-color: #ffe082;
}

li.high {
    background-color: #ff8a80;
}

li.completed {
    text-decoration: line-through;
    color: grey;
}

button.delete {
    background: red;
    color: white;
    border: none;
    cursor: pointer;
}


document.getElementById('add-task').addEventListener('click', addTask);

function addTask() {
    const taskInput = document.getElementById('new-task');
    const priorityInput = document.getElementById('priority');
    const taskText = taskInput.value.trim();
    const taskPriority = priorityInput.value;

    if (taskText === '') {
        alert('Please enter a task');
        return;
    }

    const taskList = document.getElementById('task-list');

    const li = document.createElement('li');
    li.className = taskPriority;
    li.innerHTML = `
        <span class="task-text">${taskText}</span>
        <div>
            <button class="complete">Complete</button>
            <button class="delete">Delete</button>
        </div>
    `;

    taskList.appendChild(li);

    // Clear the input
    taskInput.value = '';
    priorityInput.value = 'low';

    li.querySelector('.complete').addEventListener('click', () => {
        li.classList.toggle('completed');
    });

    li.querySelector('.delete').addEventListener('click', () => {
        taskList.removeChild(li);
    });
}
