<template>
  <div class="todo-item">
    <p>{{ text }}</p>
    <button @click="remove(id)" class="button">Remove</button>
  </div>
</template>

<script>
export default {
  props: ["item", "removeItem"],
  setup(props) {
    return {
      text: props.item.text,
      id: props.item.id,
    };
  },
  methods: {
    remove(id) {
      this.$emit("removeTodo", id);
    },
  },
};
</script>

<style scoped>
.todo-item {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-between;
  border: 2px solid #ccc;
  padding: 4px 24px;
  margin: auto;
  margin-top: 24px;
  border-radius: 8px;
  max-width: 360px;
}
.button {
  background: #e77558;
  padding: 8px 12px;
  color: #fff;
  border-radius: 8px;
  font-weight: 700;
}
</style>
