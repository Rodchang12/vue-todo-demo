<script setup>
import AddTodo from "./components/AddTodo.vue";
import TodoList from "./components/TodoList.vue"
import { ref } from "vue";

const todos = ref(
  [{
    id: 1,
    text: "Learn Vue 3",
  }
  ]);

</script>

<template>
  <div class="flex justify-center min-h-[100vh] items-center flex-col w-48 border-gray-400 border-[2px]">
    <AddTodo />
    <TodoList :todos="todos" />
  </div>
</template>
