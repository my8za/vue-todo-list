<template>
  <footer>
    <button class="btn-clear shdow" @click="clearTodo">Clear All</button>
  </footer>
</template>

<script>
export default {
  methods: {
    clearTodo: () => {},
  },
};
</script>

<style scoped>
.btn-clear {
  width: 8.5rem;
  height: 50px;
  margin: 0 auto;
  border: none;
  border-radius: 5px;
  background: #fff;
  line-height: 50px;
  color: #e20303;
}
</style>
