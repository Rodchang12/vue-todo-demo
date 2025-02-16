<script setup>
import { defineProps } from 'vue';

defineProps({
  todos: {
    type: Array
  }
});

</script>


<template>

  <ul>
    <li v-for="todo in todos" :key="todo.id">
      {{ todo.text }}
    </li>
  </ul>
</template>
