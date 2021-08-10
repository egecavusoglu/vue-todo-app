<template>
  <div class="">
    <input
      class="input"
      type="text"
      placeholder="Enter todo item..."
      v-model="enteredText"
    />
    <button @click="onAdd(this.enteredText)" class="button">Add</button>
  </div>
</template>

<script>
export default {
  props: ["onAddTodo"],
  data() {
    return {
      enteredText: "",
    };
  },
  methods: {
    onAdd(text) {
      this.enteredText = "";
      this.onAddTodo(text);
    },
  },
};
</script>

<style scoped>
.input {
  border: 2px solid #ccc;
  padding: 8px 12px;
  font-size: 16px;
  border-radius: 8px;
  margin-right: 12px;
}
.button {
  background: #42b883;
  padding: 10px 28px;
  color: #fff;
  font-size: 16px;
  border-radius: 8px;
  /* border: none; */
}
</style>
