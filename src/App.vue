<template>
  <div id="app">
    <Header />
    <About />
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import Header from "./components/Header";
import About from "./components/About";

@Component({
  components: {
    About,
    Header,
  }
})
export default class App extends Vue {}
</script>

<style lang="less">
@import "lib/colors.less";

body {
  font-size: 8px;
  margin: 0;
}

@media (min-width: 700px) {
  body {
    font-size: 12px;
  }
}

@media (min-width: 850px) {
  body {
    font-size: 18px;
  }
}


#app {
  background: @GRAY1;
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: @GRAY10;
}
</style>
