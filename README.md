# TypeScript_2

#TodoList Project: 
This is a small TypeScript project that implements a simple todo list manager. It’s designed to show how you can use classes and interfaces to organize data and behavior in a clean way.

#What it does:
- Add new tasks with a due date
- Mark tasks as completed
- Update the description of a task
- Remove tasks by their ID
- Filter tasks based on whether they’re completed or not
- Clear out all completed tasks in one go
- List everything that’s currently in your todo list

#How it’s built;
At the core, there’s an interface called TodoItem that defines the shape of each task (id, task, completed, dueDate). Then there’s a TodoList class that manages an array of these items and provides methods to manipulate them.

##Example usage

const myTodos = new TodoList();
myTodos.addTodo("Read a new book", new Date("2026-06-01"));
myTodos.addTodo("Gym training", new Date("2026-06-03"));
myTodos.addTodo("Shopping", new Date("2026-06-05"));

console.log("All Todos:");
myTodos.listTodos().forEach(todo => {
    console.log(`- ${todo.task} (Due: ${todo.dueDate.toDateString()})`);
});

const firstTodoId = myTodos.listTodos()[0].id;
myTodos.completeTodo(firstTodoId);
myTodos.updateTask(firstTodoId, "Finish reading the book");

console.log("\nCompleted Todos:");
myTodos.filterByCompleted(true).forEach(todo => {
    console.log(`- ${todo.task}`);
});

const secondTodoId = myTodos.listTodos()[1].id;
myTodos.removeTodo(secondTodoId);

myTodos.clearCompleted();

console.log("\nRemaining Todos:");
myTodos.listTodos().forEach(todo => {
    console.log(`- ${todo.task}`);
});

*But to run the project
- You’ll need to install Node.js and TypeScript. 

*If you don’t have TypeScript yet:
- run:  npm install -g typescript
- compile and run:  tsc todo.ts && node todo.js

#Ideas for improvement
- Save tasks to a file or database so they persist between runs
- Add priorities or categories to tasks
- Sort tasks by due date automatically
- Build a simple UI (CLI or web app) on top of this class

NOTE: This project is intentionally lightweight — it’s more of a learning exercise than a production‑ready app. But it’s a solid foundation if you want to expand it into something more powerful.
