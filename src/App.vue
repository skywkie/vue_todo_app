<script>
export default {
  data() {
    return {
      todoList: [],
      title: "",
      info: "",
    };
  },
  methods: {
    addToArray() {
      this.todoList.push({ title: this.title, info: this.info });
    },
  },
};
</script>

<template>
  <div class="container">
    <h1>Simple todo app</h1>
    <div class="input__container">
      <input @type="text" placeholder="some text" v-model="title" />
      <input @type="text" placeholder="some text" v-model="info" />
    </div>
    <button @click="addToArray()">Add todo</button>
    <div class="todo__list">
      <div class="todo__item" v-for="(todo, i) in todoList" :key="i">
        <h3>Title: {{ todo.title }}</h3>
        <p>Info: {{ todo.info }}</p>
      </div>
    </div>
  </div>
</template>

<!-- scoped - стили локальны -->
<style scoped>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  outline: none;
  border: none;
}
.container {
  display: flex;
  flex-direction: column;
}
.input__container {
  margin: 20px 0;
  display: flex;
  flex-direction: column;
  gap: 20px;
}
input {
  width: 100%;
  height: 35px;
  border-radius: 10px;
  padding: 0 10px;
}
button {
  height: 50px;
}
.todo__list {
  display: flex;
  flex-direction: column;
  align-items: start;
}
.todo__item {
  display: flex;
  flex-direction: column;
  align-items: start;
	border: 1px solid #fff;
	border-radius: 15px;
	margin: 10px 0;
	padding: 10px 20px;
	width: 100%;
}
</style>
