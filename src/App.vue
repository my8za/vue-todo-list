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
import TheFooter from "./components/TheFooter.vue";
import TodoListInput from "./components/TodoListInput.vue";
import TodoListItem from "./components/TodoListItem.vue";

export default {
  components: {
    "the-heading": TheHeading,
    "the-footer": TheFooter,
    "todo-input": TodoListInput,
    "todo-item": TodoListItem,
  },
};
</script>
