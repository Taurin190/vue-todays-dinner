<template>
  <div class="dinner">
    <img alt="Vue logo" :src="image_path">
    <h1>{{ message }}</h1>
    <button v-on:click="selectMenu" type="button" class="btn btn-primary">
      メニューを選ぶ！
    </button>
  </div>
</template>

<script>
export default {
  name: 'TodaysDinner',
  props: {
    msg: String
  },
  data() {
    return {
      message: "今日の晩御飯何にする？",
      image_path: require('../assets/gohan.png'),
      menus: [
        "カレー",
        "肉じゃが",
        "たこ焼き"
      ],
      images: [
        "curryrice.png",
        "nikujaga.png",
        "takoyaki.png"
      ]
    }
  }, 
  methods: {
    selectMenu: function() {
      const idx = Math.floor(Math.random() * this.menus.length);
      this.message="今日のメニューは" + this.menus[idx]
      this.image_path = require('../assets/' + this.images[idx])
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
