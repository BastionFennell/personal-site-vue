<template>
  <div id="app">
    <Header />
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import Header from "./components/Header";

@Component({
  components: {
    Header
  }
})
export default class App extends Vue {}
</script>

<style lang="less">
@import "lib/colors.less";

body {
  margin: 0;
}

#app {
  background: @GRAY1;
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: @GRAY10;
}
</style>
