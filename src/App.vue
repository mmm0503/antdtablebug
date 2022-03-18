<template>
  <div id="app" :style="{ '--top': `${topNum}px` }">
    <div class="appwarp">
      <hello-world></hello-world>
    </div>
    <div class="btnwarp">
      <button @click="change(-3)">top</button>
      <button @click="change(3)">bottom</button>
    </div>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
  },
  data() {
    return {
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
        this.topNum += type
      }, 1);

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
  transform: translateY(var(--top));
}
.btnwarp {
  position: fixed;
  bottom: 0;
}

.ant-table-fixed-left,
.ant-table-fixed-right {
  border: 1px solid red;
  min-height: 200px;
  transform: translateY(-50px);
  // z-index: 9999 !important;
}
.ant-table th,
.ant-table td {
}
.ant-table-fixed {
}
</style>
