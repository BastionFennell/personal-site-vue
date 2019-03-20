<template>
  <div class="header">
    <BastionTheX class="bastion-the-x" />
    <div class="caret-bounce">
      <div class="caret" />
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import BastionTheX from "./BastionTheX.vue";

@Component({
  components: {
    BastionTheX
  }
})
export default class Header extends Vue {}
</script>

<style scoped lang="less">
@import "../../lib/colors.less";

.header {
  background: white;
  box-sizing: border-box;
  height: 100vh;
  padding-top: calc(50vh - 3em);
  position: relative;
  text-align: center;
}

.header::after {
  border-color: transparent white transparent transparent;
  border-style: solid;
  border-width: 0 100vw 60px 0;
  bottom: -59px;
  content: " ";
  display: block;
  left: 0;
  position: absolute;
  z-index: 1;
}

i {
  bottom: 150px;
  color: @CYAN9;
  height: 3em;
  left: 50%;
  position: absolute;
  width: 3em;
}

.caret-bounce {
  animation-delay: 7s;
  animation-duration: 3s;
  animation-iteration-count: infinite;
  animation-name: caret-bounce;
  bottom: 100px;
  left: 50%;
  left: calc(50% - 30px);
  position: absolute;
}

.caret {
  animation-delay: 5s;
  animation-duration: 2s;
  animation-fill-mode: forwards;
  animation-name: caret;
  opacity: 0;
  position: relative;
}

.caret:before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  border-top: 30px solid @CYAN9;
  border-left: 30px solid transparent;
  border-right: 30px solid transparent;
}

.caret:after {
  content: "";
  position: absolute;
  left: 2px;
  top: 0;
  border-top: 28px solid #fff;
  border-left: 28px solid transparent;
  border-right: 28px solid transparent;
}

@keyframes caret {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}

@keyframes caret-bounce {
  0% {
    bottom: 100px;
  }
  50% {
    bottom: 60px;
  }
  100% {
    bottom: 100px;
  }
}
</style>
