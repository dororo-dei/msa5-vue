<script setup>
import { ref } from 'vue';

const activeTab = ref('프로필');
// activeTab: 현재 선택된 탭을 저장하는 변수
</script>

<template>
  <div class="tabui-container">
    <p>TabUI</p>
    <div class="tab-menu">
      <button @click="activeTab='프로필'" :class="{active: activeTab === '프로필'}">프로필</button>
      <button @click="activeTab='설정'" :class="{active: activeTab === '설정'}">설정</button>
      <button @click="activeTab='게시판'" :class="{active: activeTab === '게시판'}">게시판</button>
    </div>
  
    <p>{{ activeTab }} 페이지 입니다.</p>
    <!-- 값은 영어로 할 것 그러니 if문을 사용하는 것이 더 좋았다 -->
  </div>
</template>

<style>
.tabui-container{
  width: 800px;
  display: flex;
  flex-direction: column;
  align-items: center;
}

p{
  color: #333;
}

.tab-menu{
  background-color: none;
  padding: 20px;
}

button{
  padding: 20px 8px;
  cursor: pointer;
}

.tab-menu button{
  background-color: #f2f6f7;
  border: none;
  color: #333;
}

.tab-menu button.active{
  background-color: #fff;
  color: cornflowerblue;
  border-bottom: 2px solid cornflowerblue;
}

.tab-menu button:first-child{
  border-radius: 10px 0 0 10px;
}

.tab-menu button:last-child{
  border-radius: 0 10px 10px 0;
}
</style>