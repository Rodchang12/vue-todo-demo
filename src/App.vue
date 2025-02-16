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


const handleAddTodo = (todo) => {
  todos.value.push(todo);
};

const handleDeleteTodo = (todoId) => {
  todos.value = todos.value.filter((todo) => todo.id !== todoId);
};

const handleCheckTodo = (todoId) => {
  todos.value = todos.value.map((todo) => todo.id === todoId ? { ...todo, complete: !todo.complete } : todo);
};

</script>

<template>
  <div class="flex justify-center min-h-[100vh] items-center flex-col w-full border-gray-400 border-[2px]">
    <AddTodo @add-todo="handleAddTodo" />
    <TodoList :todos="todos" @deleteTodo="handleDeleteTodo" @checkTodo="handleCheckTodo" />
  </div>
</template>
