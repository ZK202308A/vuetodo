<script setup>

import TodoInput from "./TodoInput.vue";
import TodoList from "./TodoList.vue";
import {ref} from "vue";

let sequence = 3
const todos = ref([
  { tno:1, title: 'AAAA'},
  { tno:2, title: 'BBBB'}])

const addTodo = ( title ) => {

  const obj = {tno: sequence++, title:title}

  todos.value.push(obj)
}

const removeTodo = (tno) => {

  console.log("removeTodo :" + tno)

  const result = todos.value.filter( todo => todo.tno !== tno)

  todos.value = result
}

</script>

<template>
  <TodoInput @add=addTodo  />
  <TodoList :arr=todos @remove=removeTodo></TodoList>
</template>

<style scoped>

</style>