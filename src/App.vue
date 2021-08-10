<template>
  <h1>Todo List</h1>
  <Input :onAddTodo="addTodo" />
  <TodoList :todos="todos" @removeTodo="removeTodo" />
</template>

<script>
import TodoList from "./components/TodoList.vue";
import Input from "./components/Input.vue";
export default {
  name: "App",
  components: {
    TodoList,
    Input,
  },
  data() {
    return {
      todos: [{ text: "Your first todo", id: 1 }],
    };
  },
  methods: {
    addTodo(text) {
      this.todos.push({
        text,
        id: Math.floor(Math.random() * 1000),
      });
    },
    removeTodo(id) {
      console.log(id);
      this.todos = this.todos.filter((todo) => todo.id != id);
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
