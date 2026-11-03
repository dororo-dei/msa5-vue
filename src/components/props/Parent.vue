<script setup>
import { ref } from 'vue';
import Child from './Child.vue';

const user = ref({
  id:1,
  name: '홍길동',
  age: 20
});
const str = ref('전달 문자열');
</script>

<template>
  <h2>Parent</h2>
  <Child :item="user" :str="str"/>
  <!-- 여러개일 경우 이런식으로 나열해주면 된다 -->
</template>

<style>

</style>
