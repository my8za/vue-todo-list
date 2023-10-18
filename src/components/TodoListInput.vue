<template>
  <form @submit.prevent="handleAddTodo" class="input-box shadow">
    <input type="text" v-model="newTodoItem" />
    <button class="btn-add">+</button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      newTodoItem: "",
    };
  },
  methods: {
    clearInput() {
      this.newTodoItem = "";
    },
    handleAddTodo() {
      if (this.newTodoItem !== "") {
        let todo = { content: this.newTodoItem, done: false };
        localStorage.setItem(this.newTodoItem, JSON.stringify(todo));
        this.clearInput();
      }
    },
  },
};
</script>

<style scoped>
.input-box {
  position: relative;
  height: 50px;
  background: #fff;
  border-radius: 5px;
  line-height: 50px;
}
.input-box > input {
  width: 100%;
  padding-left: 20px;
  border-style: none;
  outline: none;
  font-size: 0.9rem;
}
.btn-add {
  position: absolute;
  top: 0;
  right: 0;
  width: 3rem;
  height: 50px;
  border: none;
  border-radius: 0 5px 5px 0;
  background: linear-gradient(to right, #6478fb, #8763fb);
  vertical-align: middle;
  font-size: 1.7rem;
  font-weight: 700;
  color: #fff;
  cursor: pointer;
}
</style>
