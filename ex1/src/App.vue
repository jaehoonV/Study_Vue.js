<template>
  <div class="menu">
    <a v-for="(m, i) in menus" :key="i">{{ m }}</a>
  </div>
  <div v-for="(pd, i) in products" :key="i">
    <img :src="require('./assets/room' + i + '.jpg')" class="img_style" />
    <h4 @click="modal_open = true" :style="스타일">{{ pd }}</h4>
    <p>{{ price[i] }} 만원</p>
    <button @click="increase(i)">허위매물신고</button>
    <span>신고수 : {{ 신고수[i] }}</span>
  </div>

  <div v-for="(d, i) in onerooms" :key="i">
    <img :src="d.image" class="img_style" />
    <h4 @click="openmodal(i)">{{ d.title }}</h4>
    <p>{{ d.price }} 원</p>
    <div class="black-bg" v-if="d.open == true">
      <div class="white-bg">
        <h4>{{ d.title }}</h4>
        <p>{{ d.content }}</p>
        <p>{{ d.price }} 원</p>
        <button @click="openmodal(i)">닫기</button>
      </div>
    </div>
  </div>

  <div>
    <p>{{ db }}하는 이유</p>
    <p>HTML에 하드코딩해놓으면 나중에 변경이 어려움</p>
    <p>Vue의 실시간 자동 렌더링을 사용하기 위함</p>
    <p>HTML 속성도 데이터바인딩 가능 (:속성="데이터이름")</p>
    <p>Vue의 HTML 반복문 &lt;태그 v-for="작명 in 몇회"&gt;</p>
    <p>Vue의 HTML 반복문을 사용할 때 :key=""를 꼭 사용해야함</p>
    <p>:key=""는 반복문을 돌린 요소를 컴퓨터가 구분하기 위해 사용</p>
    <p>버튼 클릭시 함수 실행은 v-on:click="", @click=""</p>
    <p>Vue에서 함수를 만들고 싶으면 methods:{함수(){}}안에 생성</p>
    <p>이미지를 불러오지 못할 때 이미지경로를 require()안에 넣어줌</p>
    <p>동적인 UI 만드는 법</p>
    <p>0. HTML CSS로 미리 디자인함</p>
    <p>1. UI의 현재 상태를 데이터로 저장해둠</p>
    <p>2. 데이터에 따라 UI가 어떻게 보일지 작성</p>
    <p>v-if="조건식" : 조건식이 참일 때만 HTML을 보여줌</p>
  </div>
</template>

<script>
import oneroom_data from "./post.js";

export default {
  name: "App",
  data() {
    return {
      onerooms: oneroom_data,
      신고수: [0, 0, 0, 0, 0],
      price: [60, 70, 80],
      db: "{{데이터바인딩}}",
      스타일: "color : blue",
      products: ["역삼동원룸", "천호동원룸", "마포구원룸"],
      menus: ["Home", "Shop", "about"],
    };
  },
  methods: {
    increase(i) {
      this.신고수[i]++;
    },
    openmodal(i) {
      if (this.onerooms[i].open == false) {
        this.onerooms[i].open = true;
      } else {
        this.onerooms[i].open = false;
      }
      console.log(this.onerooms[i].open);
    },
  },
  components: {},
};
</script>

<style>
body {
  margin: 0;
}
div {
  box-sizing: border-box;
}
.black-bg {
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  padding: 20px;
  top: 0;
}
.white-bg {
  width: 60%;
  background: white;
  border-radius: 8px;
  padding: 20px;
  margin: auto;
}

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

.img_style {
  width: 100%;
  margin-top: 40px;
}
</style>
