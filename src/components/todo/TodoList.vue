<script setup>

const props = defineProps(['arr'])
const emits = defineEmits(['remove'])

console.log(props)



</script>

<template>
  <h1>Todo List</h1>

  <ul>
    <li v-for="todo in props.arr" :key="todo.tno">
      {{todo.tno}} {{todo.title}}
      <button @click="() => emits('remove', todo.tno)"  >REMOVE</button>
    </li>
  </ul>

</template>

<style scoped>

</style>