<template>
  <div v-bind:class="{ 'is-complete': todo.completed }">
    <p v-on:click="toggle">{{ todo.title }}</p>
    <button @click="$emit('del-todo',todo.id)">X</button>
  </div>
</template>

<script>
export default {
  name: "ToDoItem",
  props: ["todo"],
  methods: {
    toggle() {
      this.todo.completed = !this.todo.completed;
    },
  },
};
</script>

<style scoped>
.is-complete {
  text-decoration: line-through;
}
</style>