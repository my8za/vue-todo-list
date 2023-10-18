<template>
  <ul>
    <li v-for="(todo, idx) in todoItems" :key="idx" class="shadow">
      <div>
        <input
          type="checkbox"
          id="todo-item"
          class="btn-check"
          v-model="todo.done"
          @click="handleChangeStatus(todo)"
        />
        <label for="todo-item">{{ todo.content }}</label>
      </div>
      <button class="btn-remove" @click="handleRemoveTodo(todo)">X</button>
    </li>
  </ul>
</template>

<script>
export default {
  data() {
    return {
      todoItems: [],
    };
  },
  created() {
    if (localStorage.length > 0) {
      for (let i = 0; i < localStorage.length; i++) {
        if (localStorage.key(i) !== "loglevel:webpack-dev-server") {
          this.todoItems.push(
            JSON.parse(localStorage.getItem(localStorage.key(i)))
          );
        }
      }
    }
  },
  methods: {
    handleRemoveTodo(todo) {
      localStorage.removeItem(todo);
      this.todoItems = this.todoItems.filter((item) => item !== todo);
    },
    handleChangeStatus(todo) {
      todo.done = !todo.done;
      // 갱신 -> 로컬스토리지에서 해당 투두 삭제 후 재추가
      localStorage.removeItem(todo.content);
      localStorage.setItem(todo.content, JSON.stringify(todo));
    },
  },
};
</script>

<style scoped>
ul {
  margin-top: 0;
  padding-left: 0;
  text-align: left;
  list-style-type: none;
}
li {
  display: flex;
  justify-content: space-between;
  margin: 0.5rem 0;
  padding: 0 0.9rem;
  height: 50px;
  min-height: 50px;
  background: #fff;
  border-radius: 5px;
  line-height: 50px;
}
.btn-remove {
  border: none;
  background: transparent;
  font-weight: 700;
  color: #de4343;
  cursor: pointer;
}
.btn-check {
  margin-right: 7px;
  line-height: 45px;
  color: #65acde;
}
</style>
