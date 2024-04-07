<template>
    <div class="bg-white py-6 sm:py-8 lg:py-46">
            <div class="text-center">
            </div>  

        <!-- Todo App -->
        <div class="container w-full max-w-sm p-4 bg-white border border-gray-200 rounded-lg shadow sm:p-6 dark:bg-gray-800 dark:border-gray-700">
            <header>
            <h1 class="text-4xl">Todo App</h1>
            </header>
            <section class="actions">
            <form @submit.prevent="addTask" class="add-task-form">
                <input type="text" placeholder="Add Task" v-model="task" required>
                <input type="text" placeholder="Search task" v-model="searchQuery" class="search-input" />
                <button class="add" type="submit">Add</button>
            </form>
            </section>

            <section class="tasks">
            <div v-for="todo in filteredTodos" :key="todo.id" class="task-item">
                <p :class="{ 'done': todo.status }">{{ todo.details }}</p>
                <button class="done-btn" @click="markAsDone(todo.id)" :disabled="todo.status">Done</button>
                <button class="remove-btn" @click="removeTask(todo.id)">Remove</button>
            </div>
            <button class="clear-btn" @click="clearAllTasks">Clear All Tasks</button>
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
      searchQuery: '',
      todos: [],
    };
  },
  computed: {
    filteredTodos() {
      return this.todos.filter(todo => todo.details.toLowerCase().includes(this.searchQuery.toLowerCase()));
    },
  },
  methods: {
    addTask() {
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
    text-decoration: line-through; /* Add a line-through style for completed tasks */
    color: #888; /* Optionally change the color of completed tasks */
  }
.container {
    width: 600px; /* Set your desired width */
    margin: 50px auto;
    background-color: rgb(71, 141, 187);
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
    outline: none;
}
.search-input {
    margin-bottom: 10px; /* Adjust the margin as needed */
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
.remove-btn,
.clear-btn {
    padding: 3px 6px;
    background-color: rgb(112, 112, 112);
    color: #fff;
    border: none;
    border-radius: 3px;
    cursor: pointer;
}

.done-btn {
    margin-left: auto;
    background-color: #077a22;
}

.remove-btn {
    background-color: #a71523;
}

</style>