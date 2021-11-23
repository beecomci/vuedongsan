<template>
  <div>
    <div class="menu">
      <a href="#" v-for="(item, i) in menus" :key="i">{{ item }}</a>
    </div>

    <div class="black-bg" v-if="isModalOpen">
      <div class="white-bg">
        <h4>상세페이지</h4>
        <p>상세페이지 내용</p>
        <button @click="isModalOpen = false">닫기</button>
      </div>
    </div>

    <div v-for="(item, i) in rooms" :key="i">
      <img :src="item.image" alt="방" class="room-img" />
      <h4 @click="isModalOpen = true">{{ item.title }}</h4>
      <p>{{ item.price }} 원</p>
    </div>
  </div>
</template>

<script>
import data from "./assets/data";

export default {
  name: "App",
  data() {
    // 데이터 보관함
    return {
      h4Style: "color: blue",
      products: ["역삼동원룸", "천호동원룸", "마포구원룸"],
      menus: ["Home", "Shop", "About"],
      reportNums: [0, 0, 0],
      isModalOpen: false,
      rooms: data
    };
  },
  methods: {
    increase(index) {
      this.reportNums[index]++;
    }
  },
  components: {}
};
</script>

<style>
body {
  margin: 0;
}

div {
  box-sizing: border-box;
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

.room-img {
  width: 100%;
  margin-top: 40px;
}

.black-bg {
  position: fixed;
  width: 100%;
  height: 100%;
  padding: 20px;
  background: rgba(0, 0, 0, 0.5);
}

.white-bg {
  width: 100%;
  padding: 20px;
  border-radius: 8px;
  background: white;
}
</style>
