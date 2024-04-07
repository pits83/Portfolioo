<template>
    <div class="bg-white py-6 sm:py-8 lg:py-46">
        <!-- My Diary -->
        <h1 class="text-5xl text-gray-900 dark:text-white text-center">My NotePad</h1>
        <div class="container  p-4 bg-white border border-gray-200 rounded-lg shadow sm:p-6 dark:bg-gray-500 dark:border-gray-700">
            <header>
                <h1 class="text-3xl mb-1 ">Notes</h1>
            </header>
            <section class="actions">
                <form @submit="addTask" class="add-task-form">
                    <input type="text" placeholder="Something need to do??" v-model="task" required>
                    <button class="add" type="submit">Save</button>
                </form>
            </section>

            <section class="tasks">
            <div v-for="todo in todos" :key="todo.id" class="task-item">
                <p :class="{ 'done': todo.status }">{{ todo.details }}</p>
                <button class="done-btn" @click="markAsDone(todo.id)" :disabled="todo.status">Done</button>
                <button class="remove-btn" @click="removeTask(todo.id)">Remove</button>
            </div>
            </section>
        </div>
    </div>
</template>
<script>
import { v4 as uuidv4 } from 'uuid';

export default {
  data() {
    return {
      task: '',
      todos: [],
    };
  },
  methods: {
    addTask(e) {
      e.preventDefault();
      const newTask = {
        id: uuidv4(),
        details: this.task,
        status: false,
      };
      this.todos.unshift(newTask);
      this.task = '';
    },
    removeTask(id) {
      const index = this.todos.findIndex((todo) => todo.id === id);
      if (index !== -1) {
        this.todos.splice(index, 1);
      }
    },
    markAsDone(id) {
      const todo = this.todos.find((todo) => todo.id === id);
      if (todo) {
        todo.status = true;
      }
    },
    clearAllTasks() {
      this.todos = [];
    },
  },
};

</script>
<style scoped>

body {
    font-family: 'Arial', sans-serif;
    margin: 0;
    padding: 0;
}

.done {
    text-decoration: line-through;
    color: #888;
}

.container {
    width: 600px;
    margin: 50px auto;
    background-color: rgb(71, 141, 187); /* Updated background color */
    padding: 20px;
    border-radius: 5px;
}

header {
    text-align: center;
    margin-bottom: 20px;
}

.actions {
    display: flex;
    flex-direction: column;
    margin-bottom: 20px;
}

.add-task-form {
    display: flex;
}

.add {
    margin: auto;
    width: 10%;
    font-size: 20px;
    padding: 5px 7px;
    border: none;
    border-radius: 3px;
    cursor: pointer;
}

input[type="text"] {
    margin: auto;
    width: 100%;
    margin-right: 5px;
    padding: 8px;
    border-radius: 3px;
    border: none;
    outline: none;
}

.tasks {
    border-top: 1px solid #ccc;
    padding-top: 20px;
}

.task-item {
    display: flex;
    gap: 5px;
    align-items: center;
    margin-bottom: 10px;
    border-bottom: 1px solid #eee;
    padding-bottom: 5px;
}

.done-btn,
.remove-btn {
    padding: 3px 6px;
    background-color: #000; 
    color: #fff;
    border: none;
    border-radius: 3px;
    cursor: pointer;
}

.done-btn {
    margin-left: auto;
    background-color: #2bce6f;
}

.remove-btn {
    background-color: #e96152;
}
</style>