<script setup>
import { ref, reactive } from "vue";

// component logic
// declare some reactive state here.
const counter = reactive({
   count: 0,
});
console.log(counter.count);
counter.count++;

const message = ref("Greet Me?");
console.log(message.value);
message.value = "Hello world!";
</script>

<template>
   <h1>{{ message }}</h1>
   <p>Count is: {{ counter.count }}</p>
</template>
