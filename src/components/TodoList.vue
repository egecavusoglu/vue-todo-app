<template>
  <div>
    <TodoItem
      v-for="todo in todos"
      v-bind:key="todo"
      :item="todo"
      @removeTodo="remove"
    />
  </div>
</template>

<script>
import TodoItem from "./TodoItem.vue";

export default {
  name: "TodoList",
  props: ["todos", "removeItem"],
  setup(props) {
    return {
      todoItems: props.todos,
    };
  },
  methods: {
    remove(id) {
      this.$emit("removeTodo", id);
    },
  },
  components: {
    TodoItem,
  },
};
</script>
