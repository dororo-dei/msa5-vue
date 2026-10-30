<script setup>
import { ref } from 'vue';

const count = ref(0);
</script>

<template>
  <div @click="count++" class="btn-cnt">Count is {{ count }}</div>
  <button @click="count=0">Count Reset</button>
</template>

<style>
</style>