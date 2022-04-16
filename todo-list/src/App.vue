<script>
import ToDoList from './components/ToDoList.vue'

export default {
  components: {
    ToDoList
  }
}
</script>

<template>
  <main>
    <ToDoList />
  </main>
</template>

<style>
body {
	font-family: sans-serif;
	background-color: rgb(38, 35, 54);
	color: #FFF;
	box-sizing: border-box;
}

main {
	width: 100%;
	height: 100vh;
	display: flex;
	flex-direction: column;
	align-items: center;
	padding-top: 50px;
}
</style>
