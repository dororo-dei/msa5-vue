<script setup>
</script>

<template>
  <h2>CE Child</h2>
  <button @click="$emit('addCount')">add</button>
  <button @click="$emit('multiCount', 2)">multi</button>
</template>

<style>
</style>