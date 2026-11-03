<script setup>
import { ref } from 'vue';

const activeTab = ref('profile');
</script>

<template>
  <h2>TabUI</h2>
  <div class="tab-container">
    <div class="tab-buttons">
      <button :class="{ active: activeTab === 'profile' }" @click="activeTab = 'profile'">프로필</button>
      <button :class="{ active: activeTab === 'setting' }" @click="activeTab = 'setting'">설정</button>
      <button :class="{ active: activeTab === 'posts' }" @click="activeTab = 'posts'">게시판</button>
    </div>
  </div>

  <div class="tab-content">
    <div v-if="activeTab === 'profile'">프로필 페이지 입니다.</div>
    <div v-else-if="activeTab === 'setting'">설정 페이지 입니다.</div>
    <div v-else>게시판 페이지 입니다.</div>
  </div>
</template>

<style>
.tab-container {
  max-width: 500px;
  margin: 30px auto;
  font-family: sans-serif;
  border: 1px solid #ddd;
  border-radius: 8px;
  overflow: hidden;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.05);
}

.tab-buttons {
  display: flex;
  background-color: #f1f3f5;
  border-bottom: 1px solid #ddd;
}

.tab-buttons button {
  flex: 1;
  padding: 12px;
  border: none;
  background: none;
  cursor: pointer;
  font-size: 15px;
  font-weight: bold;
  color: #495057;
  transition: all 0.2s;
}

.tab-buttons button:hover {
  background-color: #e9ecef;
}

/* 활성화된 탭 스타일 */
.tab-buttons button.active {
  background-color: #ffffff;
  color: #228be6;
  border-bottom: 3px solid #228be6;
}

.tab-content {
  padding: 20px;
  background-color: #ffffff;
  min-height: 150px;
}
</style>