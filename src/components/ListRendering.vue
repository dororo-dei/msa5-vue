<script setup>
import { ref } from 'vue';

const items = ref([
  {
    id: 1,
    kinds: '중식',
    food: '짜장면'
  },
  {
    id: 2,
    kinds: '한식',
    food: '비빔밥'
  },
  {
    id: 3,
    kinds: '일식',
    food: '돈까스'
  },
]);
// ref로 만드는 이유 : 데이터가 변경되었을 때 Vue가 그 변화를 감지하고 화면을 자동으로 업데이트하도록 만들기 위해서
</script>

<template>
  <h2>List Rendering</h2>

  <div class="container">
    <div v-for="item in items" :key="item.id" class="card">
    <!-- <div v-for="value in source" class="card"> -->
    <!-- value 변수 source 루프돌리는 원본 // 관습적으로 해당 리스트의 값을 단수형으로 작성-->
    <!-- 고유 이름을 같이 넣어줘야하기 때문에 :key로 id가져온다 -->
      <p>{{ item.kinds }}</p>
      <p>{{ item.food }}</p>
    </div>
  </div>
</template>

<style>
</style>