---
title: "Building a To-Do List App using Node.js & Oracle Cloud Database"
datePublished: Thu May 30 2024 15:25:01 GMT+0000 (Coordinated Universal Time)
cuid: clwtepg98000009laavhz0xgk
slug: building-to-do-list-app-using-oracle-db
tags: javascript, web-development, databases, full-stack

---

Hiya friends! I'm a software engineer on the Database Tools team at Oracle, here to guide you through creating a simple to-do list app using Node.js and connecting it to an *Oracle Cloud Database*. By the end of this post, you'll have a functional web app that allows you to manage your daily tasks with full CRUD (Create, Read, Update, Delete) functionality 🥰

#### Prerequisites:

* **Oracle Cloud Account**: You'll need an Oracle Cloud account to create and use an Oracle Autonomous Database.
    
* **Node.js**: Ensure you have Node.js installed on your machine. You can download it from [Node.js official website](https://nodejs.org/)
    
* **VsCode**: We'll use Visual Studio Code as our primary IDE, & we'll also be utilizing the SQL Developer extension in VsCode!
    
* **Basic understanding of JavaScript and SQL**: Some familiarity with JavaScript (especially ES6 syntax) and basic SQL is helpful 🙂
    

### Step 1: Setting Up Oracle Cloud Database

To set up your Oracle Cloud Database and connect to it from VsCode, follow these steps:

1. **Watch this Youtube video on how to set up your Oracle Cloud DB:**  
    [https://youtu.be/bmCHIJqegJo?si=WqrqYkIR1g9jYrB0](https://youtu.be/bmCHIJqegJo?si=WqrqYkIR1g9jYrB0)
    
2. **Download Client Credentials (Wallet):**
    
    * Once your database is provisioned, go to the database details page:
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1716484955991/b11cc003-bf1b-4bfc-87ef-7b5c91dd42ae.png align="center")
        
    * Click on 'Database Connection', and download the client credentials (a wallet file) by clicking on 'DB Connection':
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1716485159393/e6206b6d-eb86-49bc-bc78-47a56a96bf10.png align="center")
        
        Click 'Download Wallet':
        
        ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1716485236177/e9456eda-4374-4a29-beb4-d64010237bcd.png align="center")
        
    * **Note: don't unzip the wallet!** You'll need it as a zipped file, "*wallet.zip*", to upload it to the SQL Developer extension 👍🏼
        
        * Read this short blog-post on how to connect the database you just made to VsCode using the *SQL Developer VsCode extension*:  
            [https://www.lay.codes/blog/oracle-sql-developer-vscode-extension-set-up-guide](https://www.lay.codes/blog/oracle-sql-developer-vscode-extension-set-up-guide)
            

### Step 2: Initialize Your Project

Now that you've successfully connected your new Oracle Cloud DB to the SQL Developer VsCode extension, let's create and set up your Node.js application:

1. **Create Project Directory:**
    
    * Create a new directory for your project, e.g., *todo-app*
        
    * Navigate into this directory in your terminal or command prompt
        
2. **Initialize Node.js Project:**
    

* Run the command below to create a *package.json* file with default settings:
    
    ```bash
    npm init -y
    ```
    

**Install Required npm Packages:**

1. * Install the packages needed for the project:
        
        ```bash
        npm install express oracledb dotenv body-parser cors
        ```
        
    * Here's what each package is for:
        
        * *express*: The framework to create our server.
            
        * *oracledb*: Oracle's official Node.js driver to connect to the Oracle database.
            
        * *dotenv*: To manage environment variables from a *.env* file.
            
        * *body-parser*: Middleware to parse the body of incoming requests.
            
        * *cors*: Middleware to enable Cross-Origin Resource Sharing (CORS).
            

### Step 3: Configure your App

Now, let's setup your application to connect to your database and prepare for routing:

1. **Configure Environment Variables:**
    
    * Create a *.env* file in your project root
        
    * Add your database connection details:
        
        * retrieve your connection string from the same page where you downloaded your instance wallet in Step 1...
            
            ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1717081040632/866f2724-fc24-4650-8d70-2579b58c46b7.gif align="center")
            
        * copy your connection string like I did above and paste it in your *.env*, like so:
            
        
        ```javascript
        DB_USER=admin
        DB_PASSWORD=your_admin_password
        DB_CONNECTION_STRING=your_connection_string_from_tnsnames.ora
        ```
        
    * Make sure this *.env* file is listed in your *.gitignore* to prevent uploading sensitive information to version control!! 🔐
        
        * To create a *.gitignore*, just create a new file in the root of your project, name it "*.gitigno*re" and list the *.env*, like so: (can also add your *node\_modules/* folder so it doensn't crowd your Github repo)
            
            ```bash
            # .gitignore content
            .env
            
            # Dependencies 
            node_modules/
            ```
            
    * Let's create a new file for your server called '*server.js*' and add routes to handle CRUD operations. Here's the initial part of the server setup:
        
        ```javascript
        require('dotenv').config();
        const express = require('express');
        const oracledb = require('oracledb');
        const bodyParser = require('body-parser');
        const cors = require('cors');
        
        const app = express();
        const port = process.env.PORT || 3000;
        
        app.use(cors());
        app.use(bodyParser.json());
        app.use(express.static('public'));
        
        // Start the server
        app.listen(port, () => {
            console.log(`Server running on port ${port}`);
        });
        ```
        

### **Step 4: Create the***nodetab* Table

Before implementing CRUD operations, you'll need to create the *nodetab* table in your Oracle Cloud Database (feel free to rename this table, of course!). You can do this using the SQL Developer extension in VS Code by creating a .sql file and running the SQL below ⬇️

```javascript
CREATE TABLE nodetab (
    ID NUMBER GENERATED BY DEFAULT AS IDENTITY,
    DESCRIPTION VARCHAR2(255) NOT NULL,
    STATUS VARCHAR2(50) NOT NULL,
    PRIMARY KEY (ID)
);
```

### Step 5: Implement CRUD Operations

Now, add the CRUD functionalities to interact with the Oracle database:

1. **Read - Get all your To-Do Items:**
    
    * Add this route to your *server.js* file to fetch all tasks:
        
        ```javascript
        app.get('/items', async (req, res) => {
            let connection;
            try {
                connection = await oracledb.getConnection({
                    user: process.env.DB_USER,
                    password: process.env.DB_PASSWORD,
                    connectionString: process.env.DB_CONNECTION_STRING
                });
        
                const result = await connection.execute(`SELECT * FROM nodetab ORDER BY id DESC`, [], { outFormat: oracledb.OUT_FORMAT_OBJECT });
                res.json(result.rows);
            } catch (err) {
                console.error('Error fetching tasks:', err);
                res.status(500).json({ message: 'Error fetching data' });
            } finally {
                if (connection) {
                    await connection.close();
                }
            }
        });
        ```
        
2. **Create - Add a new To-Do Item:**
    
    * Add this route to *server.js* file to insert a new task:
        
        ```javascript
        app.post('/insert', async (req, res) => {
            let connection;
            try {
                connection = await oracledb.getConnection({
                    user: process.env.DB_USER,
                    password: process.env.DB_PASSWORD,
                    connectionString: process.env.DB_CONNECTION_STRING
                });
        
                const { description, status } = req.body;
                const sql = `INSERT INTO nodetab (description, status) VALUES (:1, :2)`;
                await connection.execute(sql, [description, status], { autoCommit: true });
                res.json({ message: 'Insert successful' });
            } catch (err) {
                console.error('Error adding task:', err);
                res.status(500).json({ message: 'Error inserting data' });
            } finally {
                if (connection) {
                    await connection.close();
                }
            }
        });
        ```
        
3. **Delete - Remove a To-Do Item:**
    
    * Add this route to *server.js* file to delete a task:
        
        ```javascript
        app.delete('/item/:id', async (req, res) => {
            let connection;
            try {
                connection = await oracledb.getConnection({
                    user: process.env.DB_USER,
                    password: process.env.DB_PASSWORD,
                    connectionString: process.env.DB_CONNECTION_STRING
                });
        
                const { id } = req.params;
                await connection.execute(`DELETE FROM nodetab WHERE id = :1`, [id], { autoCommit: true });
                res.json({ message: 'Delete successful' });
            } catch (err) {
                console.error('Error deleting task:', err);
                res.status(500).json({ message: 'Error deleting data' });
            } finally {
                if (connection) {
                    await connection.close();
                }
            }
        });
        ```
        
4. **Update - Modify an existing To-Do Item:**
    
    * Add this route to your *server.js* file to update a task:
        
        ```javascript
        app.put('/update/:id', async (req, res) => {
            let connection;
            try {
                connection = await oracledb.getConnection({
                    user: process.env.DB_USER,
                    password: process.env.DB_PASSWORD,
                    connectionString: process.env.DB_CONNECTION_STRING
                });
        
                const { id, description, status } = req.body;
                const sql = `UPDATE nodetab SET description = :description, status = :status WHERE id = :id`;
                await connection.execute(sql, { description, status, id }, { autoCommit: true });
                res.json({ message: 'Update successful' });
            } catch (err) {
                console.error('Error updating task:', err);
                res.status(500).json({ message: 'Error updating data' });
            } finally {
                if (connection) {
                    await connection.close();
                }
            }
        });
        ```
        

### Step 6: Create a Simple Frontend

In this step, let's create a basic HTML interface along with JavaScript to interact with the backend, enabling you to add, display, delete, and update tasks 🙂 The HTML and JS will include modal dialogs for adding and editing tasks, and a dynamic list to display your current tasks.

*index.html:*

```xml
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8" />
        <meta name="viewport" content="width=device-width, initial-scale=1.0" />
        <title>To-Do List App</title>
        <link rel="stylesheet" href="styles.css" />
    </head>
    <body>
        <div class="list-container">
            <section class="task-list to-do">
                <header class="list-header">
                    <h2>To-do</h2>
                    <button class="add-button" id="addTodoBtn">+</button>
                </header>
                <ul id="todoItems">
                <!-- To-do items will be populated here via JavaScript -->
                </ul>
            </section>
            <section class="task-list completed">
                <header class="list-header">
                    <h2>Completed</h2>
                </header>
                <ul id="completedItems">
                <!-- Completed items will be populated here via JavaScript -->
                </ul>
            </section>
            <section class="task-list tomorrow">
                <header class="list-header">
                    <h2>Tomorrow</h2>
                    <button class="add-button" id="addTomorrowsTaskBtn">+</button>
                </header>
                <ul id="tomorrowsItems">
                    <!-- Tomorrow's to-do items will be populated here via JavaScript -->
                </ul>
            </section>
            
        </section>
        </div>
        <!-- The Edit Modal -->
        <div id="editModal" class="modal">
            <!-- Modal content -->
            <div class="modal-content">
                <span class="close" onclick="closeModal()">&times;</span>
                <form id="editForm">
                    <label for="editDescription">Description:</label>
                    <input
                        type="text"
                        id="editDescription"
                        name="description"
                        required
                    />

                    <label for="editStatus">Status:</label>
                    <select id="editStatus" name="status" required>
                        <option value="Pending">Pending</option>
                        <option value="Completed">Completed</option>
                    </select>

                    <input type="submit" value="Update" />
                </form>
            </div>
        </div>
        <!-- The Add New Todo Modal -->
        <div id="addTodoModal" class="modal">
            <!-- Modal content -->
            <div class="modal-content">
                <span class="close" onclick="closeAddModal()">&times;</span>
                <form id="addForm">
                    <label for="addDescription">Description:</label>
                    <input
                        type="text"
                        id="addDescription"
                        name="description"
                        required
                    />
                    <input type="submit" value="Add" />
                    <!-- Inside the addForm form -->
                    <input type="hidden" id="addStatus" name="status" value="Pending" />

                </form>
            </div>
        </div>

        <script src="script.js"></script>
    </body>
</html>
```

*script.js :*

```javascript
// Function to fetch to-do items from the server
async function fetchTodos() {
    const response = await fetch("/items");
    if (response.ok) {
        const items = await response.json();
        const todoItemsContainer = document.getElementById("todoItems");
        const completedItemsContainer = document.getElementById("completedItems");
        const tomorrowsItemsContainer = document.getElementById("tomorrowsItems"); // Get the container for tomorrow's tasks

        // Clear existing items in all containers
        todoItemsContainer.innerHTML = "";
        completedItemsContainer.innerHTML = "";
        tomorrowsItemsContainer.innerHTML = ""; // Clear the container for tomorrow's tasks as well

        // Sort items into todo, completed, and tomorrow's lists
        items.forEach((item) => {
            // Create a new list item
            const itemElement = document.createElement("li");
            itemElement.setAttribute("data-id", item.ID);
            itemElement.setAttribute("data-description", item.DESCRIPTION);
            itemElement.setAttribute("data-status", item.STATUS);

            // Populate the list item with delete and edit buttons, and text span
            const deleteButton = createDeleteButton(item.ID);
            const editButton = createEditButton(item.ID);
            const textSpan = document.createElement("span");
            textSpan.textContent = item.DESCRIPTION;
            const iconContainer = document.createElement("div");
            iconContainer.classList.add("icon-container");
            iconContainer.appendChild(deleteButton);
            iconContainer.appendChild(editButton);

            if (item.STATUS === 'Completed') {
                textSpan.classList.add('completed-text');
            }

            // Append the container to the list item
            itemElement.appendChild(textSpan);
            itemElement.appendChild(iconContainer);

            // Append to the appropriate container based on the status
            if (item.STATUS === 'Pending') {
                todoItemsContainer.appendChild(itemElement);
            } else if (item.STATUS === 'Completed') {
                completedItemsContainer.appendChild(itemElement);
            } else if (item.STATUS === 'Tomorrow') {
                tomorrowsItemsContainer.appendChild(itemElement);
            }
        });
    } else {
        alert("Failed to fetch to-do items.");
    }
}

// Function to create a delete button with a trash icon
function createDeleteButton(id) {
    const deleteButton = document.createElement("button");
    deleteButton.innerHTML = "&#128465;"; // Unicode for trash can icon
    deleteButton.classList.add("icon-button"); // Add class for styling
    deleteButton.onclick = function () {
        deleteTodo(id);
    };
    return deleteButton;
}

// Function to create an edit button with a pencil icon
function createEditButton(id) {
    const editButton = document.createElement("button");
    editButton.innerHTML = "&#9998;"; // Unicode for pencil icon
    editButton.classList.add("icon-button"); // Add class for styling
    editButton.onclick = function () {
        showEditModal(id);
    };
    return editButton;
}


// Function to show the ADD NEW TO-DO MODAL
function showAddModal() {
    document.getElementById('addDescription').value = ''; // Clear previous input value
    document.getElementById('addStatus').value = 'Pending'; // Set the status to 'Pending' for today's tasks
    const modal = document.getElementById('addTodoModal');
    modal.style.display = 'block'; // Display the modal
}
document.getElementById('addTodoBtn').addEventListener('click', showAddModal);

// Function to show the ADD NEW TO-DO MODAL with the "Tomorrow" status
function showAddModalForTomorrow() {
    document.getElementById('addDescription').value = ''; // Clear previous input value
    const modal = document.getElementById('addTodoModal');
    modal.style.display = 'block'; // Display the modal
    document.getElementById('addStatus').value = 'Tomorrow'; // Set the status to 'Tomorrow'
}
// Function to close the add new todo modal
function closeAddModal() {
    const modal = document.getElementById('addTodoModal');
    modal.style.display = 'none';
}
// Event listener for the add new todo form submission
document.getElementById('addForm').addEventListener('submit', function(event) {
    event.preventDefault();
    submitData(); // Call submitData without parameters
    closeAddModal(); // Close the modal after submitting
});

// Function to delete a to-do item
async function deleteTodo(id) {
    const response = await fetch(`/item/${id}`, {
        method: "DELETE",
    });
    if (response.ok) {
        fetchTodos(); // Refresh the list
    } else {
        alert("Failed to delete item.");
    }
}
// Function to display the EDIT TO-DO ITEM modal
function showEditModal(id) {
    // Get the todo details by id, assumed to be stored in your items or retrieved from DOM
    const todo = document.querySelector(`li[data-id="${id}"]`);
    const description = todo ? todo.getAttribute('data-description') : '';
    const status = todo ? todo.getAttribute('data-status') : '';

    // Set the current todo details in the modal's form fields
    document.getElementById('editDescription').value = description;
    document.getElementById('editStatus').value = status;

    // Show the modal
    const modal = document.getElementById('editModal');
    modal.style.display = 'block';

    // Set the form's onsubmit event
    const form = document.getElementById('editForm');
    form.onsubmit = function (event) {
        event.preventDefault();
        submitEdit(id);
    };
}
// Event listener for ADD TO-DO modal button
document.getElementById('addTomorrowsTaskBtn').addEventListener('click', showAddModalForTomorrow);

// Function to close the modal
function closeModal() {
    const modal = document.getElementById('editModal');
    modal.style.display = 'none';
}

// Function to handle the form submission for editing a todo
function submitEdit(id) {
    const description = document.getElementById('editDescription').value;
    const status = document.getElementById('editStatus').value;

    // Prepare the request body
    const requestBody = {
        id: id,
        description: description,
        status: status,
    };

    // Send the PUT request to the server
    fetch(`/update/${id}`, {
        method: "PUT",
        headers: {
            "Content-Type": "application/json",
        },
        body: JSON.stringify(requestBody),
    })
    .then(response => response.json())
    .then(data => {
        closeModal(); // Close the modal
        fetchTodos(); // Refresh the list to show the updated item
        alert("Item updated successfully.");
    })
    .catch((error) => {
        console.error("Error updating item:", error);
        alert("Failed to update item.");
    });
}


// Function to submit new to-do item
async function submitData() {
    // Retrieve the description and status from the modal inputs
    const description = document.getElementById('addDescription').value;
    const status = document.getElementById('addStatus').value; // Retrieve the status from the hidden input

    const requestBody = { description, status };
    
    const response = await fetch("/insert", {
        method: "POST",
        headers: {
            "Content-Type": "application/json",
        },
        body: JSON.stringify(requestBody),
    });
    
    if (response.ok) {
        fetchTodos(); // Refresh the list
        closeAddModal(); // Close the modal after successful insertion
        alert("Data inserted successfully");
    } else {
        alert("Failed to insert data");
    }
}

document.addEventListener('DOMContentLoaded', function() {
    var calendarEl = document.getElementById('calendar');
    var calendar = new FullCalendar.Calendar(calendarEl, {
        initialView: 'dayGridMonth',
        // Add other options as needed
    });
    calendar.render();
});

// Fetch and display todos when the page loads
window.onload = fetchTodos;
```

And lastly, add whatever *.css* you'd like to give it a personal style! 🎨 Here's what my to-do app looks like:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1716486302611/b222dd7b-16df-410c-bc68-e4d0aeb7fa5a.gif align="center")

And this is what your file structure should be looking like, for reference:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1717081985535/b4062d84-8100-4e34-8069-ade6c8169185.png align="center")

---

And voila, you've now created a full-stack to-do list app using Oracle Cloud Database! Easy, right? 😊 The Database Tools team did an amazing job with the SQL Developer VsCode extension, making it incredibly user-friendly. We're also revamping Oracle's SQL tutorial-based playground, LiveSQL, which I can't wait to share more about once it launches!

Feel free to reach out if you need more details or assistance on specific parts of this project. I'm happy to help! 🧡

Connect with me at [lay.codes](https://lay.codes), and check out [lay.codes/blog](https://lay.codes/blog) or my [Youtube](https://www.youtube.com/@pilatesdev) for more how-to videos/blogposts! Happy coding!