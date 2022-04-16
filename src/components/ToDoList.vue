<script>
export default {
  data() {
    return {
      todo: '',
      savedTodo: []
    }
  },
  methods: {
    saveTodoList() {
      this.savedTodo.push(this.todo)
      this.todo = ''
    },
    deleteTodoList(index) {
      this.savedTodo.splice(index, 1)
    }
  }
}
</script>


<template>
  <section>
    <section class="todo">
      <h1 class="todo__title">Todo List App</h1>
      <p>Create a list of tasks</p>
      <div class="todo__action">
        <input class="todo__input" type="text" v-model="todo" @keyup.enter="saveTodoList">
        <button class="todo__save" @click="saveTodoList">Save</button>
      </div>
    </section>

    <section class="list">
      <div class="list__task" v-for="(todo, index) in savedTodo" :key="index">
        <div class="list__content">{{ todo }}</div>
        <button class="list__delete" @click="deleteTodoList(index)">Delete</button>
      </div>
    </section>
  </section>
</template>

<style scoped>
.todo__title {
  font-size: 50px;
  margin-bottom: 10px;
}

.todo__action {
  display: flex;
  justify-content: center;
  align-items: center;
}

.todo__input {
  border: none;
  outline: none;
  border-bottom: 1px solid #FFF;
  background-color: transparent;
  color: #FFF;
  font-size: 25px;
  padding: 10px 0;
}

.todo__input:focus {
  border-bottom: 1px solid rgb(47, 214, 111);
}

.todo__save {
  border: none;
  outline: none;
  background-color: rgb(47, 214, 111);
  font-weight: bold;
  font-size: 25px;
  padding: 12px;
  border-radius: 10px;
  margin-left: 10px;
  cursor: pointer;
}

.list {
  width: 100%;
  margin-top: 20px;
}

.list__task {
  display: flex;
  align-items: center;
  justify-content: space-between;
  background-color: rgb(52, 47, 78);
  padding: 20px;
  border-radius: 10px;
  margin-bottom: 15px;
}

.list__delete {
  border: none;
  outline: none;
  background-color: crimson;
  color: #EEE;
  font-weight: bold;
  font-size: 15px;
  padding: 10px 15px;
  border-radius: 10px;
  cursor: pointer;
}
</style>
