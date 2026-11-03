<script setup>
import { onBeforeMount, onMounted } from 'vue';


onBeforeMount(()=>{
  alert('마운트 전에 실행됩니다.')
});
onMounted(()=>{
  alert('마운트 후에 실행됩니다.')
});
</script>

<template>
  <h2>Life Cycle</h2>
</template>

<style scoped>

</style>