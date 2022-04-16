<template>
  <div class="menu">
    <a v-for="(m, i) in menus" :key="i">{{ m }}</a>
  </div>
  <div v-for="(pd, i) in products" :key="i">
    <h4 :style="스타일">{{ pd }}</h4>
    <p>{{ price[i] }} 만원</p>
  </div>
  <div>
    <p>{{ db }}하는 이유</p>
    <p>HTML에 하드코딩해놓으면 나중에 변경이 어려움</p>
    <p>Vue의 실시간 자동 렌더링을 사용하기 위함</p>
    <p>HTML 속성도 데이터바인딩 가능 (:속성="데이터이름")</p>
    <p>Vue의 HTML 반복문 &lt;태그 v-for="작명 in 몇회"&gt;</p>
    <p>Vue의 HTML 반복문을 사용할 때 :key=""를 꼭 사용해야함</p>
    <p>:key=""는 반복문을 돌린 요소를 컴퓨터가 구분하기 위해 사용</p>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      price: [60, 70, 80],
      db: "{{데이터바인딩}}",
      스타일: "color : blue",
      products: ["역삼동원룸", "천호동원룸", "마포구원룸"],
      menus: ["Home", "Shop", "about"],
    };
  },
  components: {},
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}

.menu a {
  color: white;
  padding: 10px;
}
</style>
