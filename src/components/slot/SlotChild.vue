<script setup>
</script>

<template>
  <h2>Slot Child</h2>
  <button type="button">
    <slot>기본 버튼</slot>
    <!-- 부모한테서 받아오려면 slot태그 가져오기 -->
     <!-- 부모쪽에서 템플릿 정보 안보냈을 때 자식이 슬롯을 이용해서 기본 세팅을 출력 -->
  </button>
</template>

<style scoped>

</style>