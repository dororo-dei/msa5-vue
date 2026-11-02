<script setup>
import { ref } from 'vue';

const count = ref(0);
const bgColor = ref('');
// => bgColor안에 ''빈문자열이 들어있는게 아니라 ref객체가 들어가있는 것
const email = ref('aaa');

const toggleBgColor = () => {
  if(bgColor.value === '') {
    bgColor.value = 'bg-red';
  } else {
    bgColor.value = '';
  }
}
</script>

<template>
  <div @click="count++" class="btn-cnt" :class="bgColor">Count is {{ count }}</div>
  <button @click="count=0">Count Reset</button>
  <button @click="count--">Count Down</button>
  <button @click="bgColor = 'bg-red'">Red</button>
  <button @click="bgColor = ''">cadetblue</button>
  <button @click="toggleBgColor()">Toggle</button>
  <br>
  <br>
  <input type="text" name="email" id="email" v-model="email">
  {{ email }}
</template>

<style>
.btn-cnt{
  background-color: cadetblue;
}
.bg-red{
  background-color: #f00;
}
</style>