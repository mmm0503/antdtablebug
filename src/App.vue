<template>
  <div id="app" :style="{ '--top': `${topNum}px` }">
    <div class="appwarp">
      <component :is="com"></component>
    </div>
    <div class="btnwarp">
      <button @click="change(3)">top</button>
      <button @click="change(-3)">bottom</button>
    </div>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import HeWord from './components/HeWord.vue'

export default {
  name: 'App',
  components: {
    HelloWorld, HeWord
  },
  data() {
    return {
      com: 'HelloWorld',
      topNum: 0,
      topt: null
    }
  },
  mounted() {
  },
  methods: {
    change(type) {
      if (this.topt) {
        clearInterval(this.topt)
        this.topt = null
      }
      else this.topt = setInterval(() => {
        this.topNum -= type
      }, 10);
    }

  },
}
</script>

<style lang="less">
html {
  --top: 0px;
}
.appwarp {
  height: 100vh;
  // padding-top: 200px;
  transform: translateY(var(--top));
}
.btnwarp {
  position: fixed;
  bottom: 0;
  z-index: 999;
}
</style>
