<script setup>
import { ref } from 'vue'

const todoItem = ref({
  id: 1, todo: "sweeping the floor", done: false
})

</script>

<template>
  <div :style="{ backgroundColor: 'lightblue', display: 'flex', gap: '8px' }">
    <input type="checkbox" v-model="todoItem.done" :id="'todo-' + todoItem.id" />
    
    <label :for="'todo-' + todoItem.id">
      <h1 :class="{ doneStyle: todoItem.done }">
        {{ todoItem.todo }}
      </h1>
    </label>
  </div>
  <p>Status: {{ todoItem.done ? 'DONE' : 'PENDING' }}</p>
</template>

<style scoped>
/* Optional: Style to visually indicate the 'done' state */
.doneStyle {
  text-decoration: line-through;
  color: #888;
}
</style>