<template>
  <div>
    <h1>Transition</h1>
    <button @click="toggleShow">Toggle</button>
    <Transition>
      <p v-if="show === true">hello</p>
    </Transition>
  </div>
</template>

<script setup>
import { ref } from "vue";
import { computed } from "vue";

  const i = 0
  const show = ref(false)
  const toggleShow = () => {
    show.value = !show.value
  }

</script>

<style scoped>
  .v-enter-active,
  .v-leave-active {
    transition: opacity 0.5s ease;
  }

  .v-enter-from,
  .v-leave-to {
    opacity: 0
  }
</style>

