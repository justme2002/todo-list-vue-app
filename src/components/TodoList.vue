<template>
  <div class="todo-item">
    <input type="checkbox"
      name=""
      id=""
      @change="$emit('tickTodo', todo.id)"
    >
    <li :class="todo.completed ? 'completed-todo' : ''">
      {{ todo.title }}
    </li>
    <div class="delete-button">
      <button @click="$emit('deleteTodo', todo.id)">delete</button>
    </div>
  </div>
</template>

<script setup>
import { computed } from "@vue/runtime-core"

  defineProps({
    todo: Object
  })

  defineEmits([
    'deleteTodo',
    'tickTodo'
  ])

  

  
</script>

<style scoped>
  .todo-item {
    list-style: none;
    font-family:'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
    display: flex;
  }

  .completed-todo {
    text-decoration: line-through;
  }

  .delete-button {
    justify-content: flex-end;

  }
</style>