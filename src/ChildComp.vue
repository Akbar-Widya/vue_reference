<script setup>
const props = defineProps({
   msg: String
})
</script>
<template>
   <h2>{{ msg || 'Bo props passed yet' }}</h2>
</template>