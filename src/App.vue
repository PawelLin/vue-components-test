<template>
  <div id="app">
    <img src="./assets/logo.png">
    <div>
      <p>
        If Element is successfully added to this project, you'll see an
        <code v-text="'<el-button>'"></code>
        below
      </p>
      <el-button>el-button</el-button>
      <pw-button/>
      <div>
        <img @click="showPreview(index)" v-for="(item, index) in images" :src="item" :alt="item" :key="item + index" width="80">
      </div>
      <pw-image-preview v-model="show" :images="images" :startPosition="startPosition"></pw-image-preview>
      <pw-pie-chart></pw-pie-chart>
    </div>
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'app',
  components: {
    HelloWorld
  },
  data () {
    return {
      show: false,
      images: [
        'http://game.gtimg.cn/images/yxzj/img201606/skin/hero-info/152/152-bigskin-4.jpg',
        'http://game.gtimg.cn/images/yxzj/img201606/skin/hero-info/141/141-bigskin-4.jpg',
        'http://game.gtimg.cn/images/yxzj/img201606/skin/hero-info/176/176-bigskin-2.jpg',
        'http://game.gtimg.cn/images/yxzj/img201606/skin/hero-info/523/523-bigskin-2.jpg'
      ],
      startPosition: 0
    }
  },
  methods: {
    showPreview (index) {
      this.startPosition = index
      this.show = true
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
