<script setup>
import SlotChild from './SlotChild.vue';

</script>

<template>
  <h2>Slot Parent</h2>
  <SlotChild>부모에서 보낸 버튼</SlotChild>
  <SlotChild>전송</SlotChild>
  <SlotChild></SlotChild>
  <!-- 왜 slot이 여는태그 닫는태그 따로 작성하느냐? 부모쪽에서 작성한 템플릿 정보를 자식 컴포넌트에게 전달하기위해 -->
</template>

<style>

</style>