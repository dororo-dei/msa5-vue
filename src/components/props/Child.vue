<script setup>
import { defineProps } from 'vue';

const props = defineProps ({
  // 받을 때 객체로 받는다 어떻게? 부모쪽에서 지정한 key를 문자열로 받아옴
  'item' : Object, // 부모로부터 받는 데이터타입 기입
  'str' : String // 객체 타입 
});
</script>

<template>
  <h2>Child</h2>
  <!-- 부모쪽에서 가져온건 읽기전용 그래서 자식쪽에서 수정 불가능 -->
  <!-- 부모쪽에서 있는 데이터를 자식쪽에 가져와서 이런식으로 이용 가능하다 -->
  <p>{{ props.item.name}}</p>
</template>

<style>

</style>
