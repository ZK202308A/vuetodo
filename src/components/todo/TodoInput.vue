<script setup>

import {ref} from "vue";

const text = ref('')

const emits = defineEmits(['add'])

const handleClick = () => {

  emits('add', text.value)

  text.value =''
}

</script>

<template>

  <div>
    <h2>Todo Input</h2>

    <input type="text" v-model=text>
    <button @click=handleClick>SEND</button>
  </div>

</template>

<style scoped>

</style>