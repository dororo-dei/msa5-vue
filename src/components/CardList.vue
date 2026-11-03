<script setup>
import axios from 'axios';
import { onBeforeMount, ref } from 'vue';

// 리스트 형식은 배열, 그외는 객체 등등
// null이나 빈배열로 한다
// java라면 null / js는 null로 만들때의 불편함이 많다
// 변수 선언
const cards = ref([]);
const page = ref(1);
const limit = 3; 
// limit은 반응형 state로 만들 필요없어
// ref 객체는 데이터바인딩 하고싶을 때만 사용 그러니 반응형으로 만들 필요없는 고정값이라면 사용하지 않기~!

// 함수선언
const getNextPage = async ()=>{
  try {
    const url = 'https://picsum.photos/v2/list';
    const config = {
      params: {
        page: page.value,
        limit
      }
    }
    const response = await axios.get(url, config)
    cards.value.push(...response.data);

    page.value++;
  } catch(error){
    console.error(error)
  }
}

const reset = () => {
  // cards.value = [];
  // page.value = 1;
  // getNextPage(); // 네트워크 트래픽으로인해 선호되진않는 방식 (싹다지우고 화면 다시불러오는데 텀이 있음)

  // cards.value.splice(0, limit); // 0부터가 아니라 3부터 나옴
  // cards.value.splice(limit, cards.value.length - limit);
  cards.value = cards.value.slice(0,limit); // slice: 특정위치잘라서 없애는거
  page.value=2; // 1페이지는 남겨뒀으니까 다음 페이지를 가져올 때 2페이지 부터 가져와야하니까~
}

// 라이프 사이클 훅스
onBeforeMount(getNextPage);
</script>

<template>
  <div class="card-container">
    <div v-for="item in cards" :key="item.id" class="card">
      <div class="card-img" :style="{backgroundImage: `url(${item.download_url})`}"></div>
      <div class="card-text">{{ item.id }}: {{ item.author }}</div>
    </div>
  </div>

  <div>
    <button @click="getNextPage">다음 페이지</button>
    <button @click="reset">리셋</button>
  </div>
</template>

<style scoped>
.card-container{
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
  gap: 10px;
}
.card{
  display: flex;
  flex-direction: column;
  gap: 10px;
}
.card-img{
  aspect-ratio: 4/3;
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
}
</style>