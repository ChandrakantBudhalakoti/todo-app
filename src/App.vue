<template>
  <div id="app">
    <header>
      <h1>My Todo App</h1>
    </header>
    <main>
      <AddTodo @add-todo="addTodo" />
      <TodoList :todos="todos" @remove-todo="removeTodo" />
    </main>
  </div>
</template>

<script>
import AddTodo from './components/AddTodo.vue';
import TodoList from './components/TodoList.vue';

export default {
  name: 'App',
  components: {
    AddTodo,
    TodoList
  },
  data() {
    return {
      todos: []
    };
  },
  methods: {
    addTodo(newTodo) {
      this.todos.push(newTodo);
    },
    removeTodo(index) {
      this.todos.splice(index, 1);
    }
  }
};
</script>

<style>
body {
  background-color: #f0f8ff;
  font-family: 'Arial', sans-serif;
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

header {
  background-color: #3b5998;
  color: white;
  padding: 20px;
  text-align: center;
}

h1 {
  margin: 0;
}

main {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin: 20px;
}

#app {
  max-width: 600px;
  margin: 0 auto;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}
</style>
