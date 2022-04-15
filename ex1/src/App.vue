<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <div>
    <h4 :style="스타일">{{ products[0] }}</h4>
    <p>{{ price1 }} 만원</p>
  </div>
  <div>
    <h4 :style="스타일">{{ products[1] }}</h4>
    <p>{{ price2 }} 만원</p>
  </div>
  <div>
    <h4 :style="스타일">{{ products[2] }}</h4>
    <p>{{ price3 }} 만원</p>
  </div>
  <div>
    <p>{{ db }}하는 이유</p>
    <p>HTML에 하드코딩해놓으면 나중에 변경이 어려움</p>
    <p>vue의 실시간 자동 렌더링을 사용하기 위함</p>
    <p>HTML 속성도 데이터바인딩 가능 (:속성="데이터이름")</p>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      price1: 60,
      price2: 70,
      price3: 80,
      db: "{{데이터바인딩}}",
      스타일: "color : blue",
      products: ["역삼동원룸", "천호동원룸", "마포구원룸"],
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
  margin-top: 60px;
}
</style>
