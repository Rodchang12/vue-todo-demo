<script setup>
import { ref, defineEmits } from "vue";

const newTodo = ref("");

const emit = defineEmits(["add-todo"]);


const addTodo = () => {
  const todo = {
    id: crypto.randomUUID(),
    text: newTodo.value,
    complete: false
  };
  emit("add-todo", todo);
};



</script>


<template>
  <form id="form" @submit.prevent="addTodo">
    <div>
      <input type="text" placeholder="Todo text ..." class="bg-testColor border-[2px] text-gray p-4 rounded-sm text-lg"
        v-model="newTodo" />
    </div>


    <div class="mt-2">
      <button class="bg-blue-500 text-white p-4 rounded-sm w-full">Add</button>
    </div>
  </form>
</template>
