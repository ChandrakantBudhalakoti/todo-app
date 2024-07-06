<template>
  <div class="todo-list">
    <TodoItem
      v-for="(todo, index) in todos"
      :key="index"
      :todo="todo"
      @remove="removeTodo(index)"
    />
  </div>
</template>

<script>
import TodoItem from "./TodoItem.vue";

export default {
  name: "TodoList",
  components: {
    TodoItem,
  },
  props: {
    todos: Array,
  },
  methods: {
    removeTodo(index) {
      this.$emit("remove-todo", index);
    },
  },
};
</script>

<style scoped>
.todo-list {
  width: 100%;
}
</style>
x
