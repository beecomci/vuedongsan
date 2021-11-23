<template>
  <div>
    <div class="menu">
      <a href="#" v-for="(item, i) in menus" :key="i">{{ item }}</a>
    </div>
    <img alt="Vue logo" src="./assets/logo.png" />
    <div v-for="(item, i) in products" :key="i">
      <h4 :style="h4Style">{{ item }}</h4>
      <p>50 만원</p>
      <button @click="increase(i)">허위매물신고</button>
      <span>신고수 : {{reportNums[i]}}</span>
    </div>
    <!-- <div>
      <h4 :style="h4Style">{{products[0]}}</h4>
      <p>50 만원</p>
      <button @click="increase">허위매물신고</button>
      <span>신고수 : {{reportNum}}</span>
    </div>
    <div>
      <h4 :style="h4Style">{{products[1]}}</h4>
      <p>50 만원</p>
    </div>
    <div>
      <h4 :style="h4Style">{{products[2]}}</h4>
      <p>50 만원</p>
    </div>-->
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    // 데이터 보관함
    return {
      h4Style: "color: blue",
      products: ["역삼동원룸", "천호동원룸", "마포구원룸"],
      menus: ["Home", "Shop", "About"],
      reportNums: [0, 0, 0]
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
