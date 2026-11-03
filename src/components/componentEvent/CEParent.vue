<script setup>
import { ref } from 'vue';
import CEChild from './CEChild.vue';

const count = ref(0);

const addCount = () => {
  count.value++;
}

// 이때는 파라미터를 받아야한다
// 자식쪽에 전달할 땐 동일
const multiCount = (val) => {
  count.value *= val;
}
</script>

<template>
  <h2>CE Parent</h2>
  <p>카운트: {{ count }}</p>

  <CEChild @addCount="addCount" @multiCount="multiCount"/>
</template>

<style>
</style>