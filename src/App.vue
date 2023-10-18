<template>
  <div id="app">
    <the-heading></the-heading>
    <todo-input></todo-input>
    <todo-item></todo-item>
    <the-footer></the-footer>
  </div>
</template>

<script>
import TheHeading from "./components/TheHeading.vue";
import TodoListInput from "./components/TodoListInput.vue";
import TodoListItem from "./components/TodoListItem.vue";
import TheFooter from "./components/TheFooter.vue";

export default {
  components: {
    "the-heading": TheHeading,
    "the-footer": TheFooter,
    "todo-input": TodoListInput,
    "todo-item": TodoListItem,
  },
};
</script>

<style>
body {
  background: #f6f6f6;
  text-align: center;
}
input,
button {
  border-style: groove;
}
.shadow {
  box-shadow: 5px 10px 5px rgba(0, 0, 0, 0.03);
}
</style>
