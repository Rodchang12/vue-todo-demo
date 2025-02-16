<script setup>
import { defineProps, defineEmits } from 'vue';

defineProps({
  todos: {
    type: Array
  }
});

const emit = defineEmits(["deleteTodo", "checkTodo"]);

const deleteTodo = (todoId) => {
  emit("deleteTodo", todoId);
};

const checkTodo = (todoId) => {
  emit("checkTodo", todoId);
};


</script>


<template>
  <ul v-if="todos.length > 0" class="w-full flex flex-col items-center">
    <li v-for="(todo, index) in todos" :key="todo.id"
      class="flex gap-2 my-2 border p-[8px] border-gray-400 w-[50vh] rounded-sm">
      <button class="bg-red-500 w-6 rounded" @click="deleteTodo(todo.id)">X</button>
      <button class="bg-green-500 w-6 rounded" @click="checkTodo(todo.id)">V</button>
      <p>{{ index + 1 }}.</p>
      <p :class="{ 'line-through': todo.complete }">{{ todo.text }}</p>
    </li>
  </ul>
  <h2 v-else class="border p-[8px]">尚無代辦事項</h2>

</template>
