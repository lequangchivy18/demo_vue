<template>
  <div id="app">
    <h1>Todo List</h1>
    <ul>
      <li v-for="todo in todos" v-bind:key="todo.text">
        {{ todo.text }}
        <button @click="deleteTodo(todo)">Delete</button>
      </li>
    </ul>
    <input v-model="newTodoText" placeholder="Add a new todo">
    <button @click="addTodo">Add Todo</button>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      todos: [
        { text: 'Buy milk' },
        { text: 'Do laundry' },
        { text: 'Clean the house' }
      ],
      newTodoText: ''
    }
  },
  methods: {
    deleteTodo(todo) {
      this.todos.splice(this.todos.indexOf(todo), 1);
    },
    addTodo() {
      this.todos.push({ text: this.newTodoText });
      this.newTodoText = '';
    }
  }
};
</script>

<style>
body {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  margin: 0;
  padding: 0;
}

#app {
  font-size: 16px;
  line-height: 1.5;
  color: #2c3e50;
  margin: 10px auto;
  max-width: 960px;
}

ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
}

li {
  margin-bottom: 10px;
}

button {
  margin-right: 10px;
}
</style>
