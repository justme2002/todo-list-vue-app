<template>
  <div>
    <Header />
    <TodoForm 
      :todoInput="todoInput"
      @addTodo="addTodo"
    />
    <div v-for="todo in todos" :key="todo.id">
      <TodoList 
        :todo="todo"
        @deleteTodo="deleteTodo"
        @tickTodo="tickTodo"
      />
    </div>
    <!-- <TransitionComponent /> -->
  </div>  
</template>

<script setup>
import Header from './components/Header.vue'
import TodoList from './components/TodoList.vue'
import TodoForm from './components/TodoForm.vue'
import TransitionComponent from './components/TransitionComponent.vue'
import { ref } from 'vue'

let todos = ref([
    {
      id: 1,
      title: "viec 1",
      completed: false
    },
    {
      id: 2,
      title: "viec 2",
      completed: false
    },
    {
      id: 3,
      title: "viec 3",
      completed: false
    }
  ])

  const todoInput = ref("")

const tickTodo = (id) => {
  console.log(id)
  todos.value = todos.value.map(todo => {
    if (todo.id === id) {
      todo.completed = !todo.completed
    }
    return todo
  })
}

const deleteTodo = (id) => {
  console.log(id)
  todos.value = todos.value.filter(todo => todo.id !== id)
}

const addTodo = (todo) => {
  todos.value = [...todos.value, todo]
}


</script>

<style>

</style>