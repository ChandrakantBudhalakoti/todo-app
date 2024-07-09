<template>
  <div class="add-todo">
    <input type="text" v-model="newTodo" placeholder="Add a new task" @keyup.enter="submitTodo" />
    <button @click="submitTodo">Add</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      newTodo: ''
    };
  },
  methods: {
    submitTodo() {
      if (this.newTodo.trim()) {
        this.$emit('add-todo', this.newTodo);
        this.newTodo = '';
      }
    }
  }
};
</script>

<style scoped>
.add-todo {
  display: flex;
  margin-bottom: 20px;
}

input {
  flex: 1;
  padding: 10px;
  font-size: 16px;
  border: 2px solid #3b5998;
  border-radius: 5px;
  margin-right: 10px;
}

button {
  padding: 10px 20px;
  background-color: #3b5998;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.3s;
}

button:hover {
  background-color: #2d4373;
}
</style>
