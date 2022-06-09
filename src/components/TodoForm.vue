<template>
  <div>
    <form @submit.prevent="$emit('addTodo', {
      id: uuidv4(),
      title: todoInput,
      completed: false,
    })">
      <div>
        <label for="add_todo">add todo</label>
        <input type="text" name="add_todo" v-model="todoInput">
        <button type="submit">add todo</button>
        {{ todoInput }}
      </div>
    </form>
  </div>
</template>

<script setup>
import { ref } from "@vue/reactivity";
import { v4 as uuidv4 } from 'uuid'

  // const submitTodo = () => {

  // }

  defineProps({
    todoInput: String
  })

  defineEmits([
    'addTodo'
  ])
  
</script>

<style>

</style>