<template>
  <div class="todo-item">
    <span>{{ todo }}</span>
    <button @click="$emit('remove')">Remove</button>
  </div>
</template>

<script>
export default {
  name: 'TodoItem',
  props: {
    todo: String
  }
};
</script>

<style scoped>
.todo-item {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: #fff;
  padding: 10px;
  border: 1px solid #ddd;
  border-radius: 5px;
  margin-bottom: 10px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

button {
  background-color: #ff6347;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  padding: 5px 10px;
  transition: background-color 0.3s;
}

button:hover {
  background-color: #e5533d;
}
</style>
