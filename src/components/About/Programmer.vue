<template>
  <div class="programmer">
    <div class="head" />
    <div class="body" />
    <div class="right-arm-upper" />
    <div class="right-arm-lower" />
    <div class="left-arm-upper" />
    <div class="left-arm-lower" />
    <div class="laptop-top" />
    <div class="laptop-bottom" />
    <div class="laptop-logo" />
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";

@Component
export default class Programmer extends Vue {}
</script>

<style scoped lang="less">
@import "../../lib/colors.less";

.programmer {
  height: 30vw;
  position: relative;
  width: 100vw;
}

.head {
  background-color: pink;
  border-radius: 50%;
  height: 40%;
  left: 45%;
  position: absolute;
  top: 10%;
  width: 12%;
  z-index: 3;
}

.body {
  background-color: @CYAN5;
  border-top-left-radius: 50%;
  border-top-right-radius: 50%;
  height: 70%;
  left: 41%;
  position: absolute;
  top: 30%;
  width: 20%;
  z-index: 1;
}

.right-arm-upper {
  animation-duration: 0.5s;
  animation-iteration-count: infinite;
  animation-name: right-arm-upper;
  background-color: @CYAN6;
  border-radius: 100px;
  height: 20%;
  left: 32%;
  position: absolute;
  top: 46%;
  transform: rotate(-20deg);
  width: 15%;
  z-index: 2;
}

.right-arm-lower {
  animation-duration: 0.5s;
  animation-iteration-count: infinite;
  animation-name: right-arm-lower;
  background-color: @CYAN6;
  border-radius: 100px;
  height: 20%;
  left: 32%;
  position: absolute;
  top: 57%;
  transform: rotate(20deg);
  width: 15%;
  z-index: 4;
}

.left-arm-upper {
  animation-duration: 0.5s;
  animation-iteration-count: infinite;
  animation-name: left-arm-upper;
  background-color: @CYAN6;
  border-radius: 100px;
  height: 20%;
  left: 55%;
  position: absolute;
  top: 35%;
  transform: rotate(-20deg);
  width: 15%;
  z-index: 2;
}

.left-arm-lower {
  animation-duration: 0.5s;
  animation-iteration-count: infinite;
  animation-name: left-arm-lower;
  background-color: @CYAN6;
  border-radius: 100px;
  height: 20%;
  left: 55%;
  position: absolute;
  top: 23%;
  transform: rotate(20deg);
  width: 15%;
  z-index: 4;
}

.laptop-top {
  animation-duration: 0.5s;
  animation-iteration-count: infinite;
  animation-name: laptop-top;
  background-color: @GRAY6;
  border-radius: 6px;
  left: 41%;
  width: 20%;
  height: 40%;
  position: absolute;
  top: 57%;
  z-index: 5;
}

.laptop-bottom {
  animation-duration: 0.5s;
  animation-iteration-count: infinite;
  animation-name: laptop-bottom;
  background-color: @GRAY6;
  left: 41%;
  width: 20%;
  height: 3%;
  position: absolute;
  top: 97%;
  z-index: 5;
}

.laptop-logo {
  background-color: @GREEN5;
  left: 49%;
  top: 70%;
  border-radius: 100px;
  height: 16%;
  position: absolute;
  width: 5%;
  z-index: 6;
}

@keyframes left-arm-lower {
  0% {
    top: 23%;
    transform: rotate(20deg);
  }
  50% {
    top: 57%;
    transform: rotate(-20deg);
  }
  100% {
    top: 23%;
    transform: rotate(20deg);
  }
}

@keyframes left-arm-upper {
  0% {
    top: 35%;
    transform: rotate(-20deg);
  }
  50% {
    top: 46%;
    transform: rotate(20deg);
  }
  100% {
    top: 35%;
    transform: rotate(-20deg);
  }
}

@keyframes right-arm-lower {
  0% {
    top: 57%;
    transform: rotate(20deg);
  }
  50% {
    top: 23%;
    transform: rotate(-20deg);
  }
  100% {
    top: 57%;
    transform: rotate(20deg);
  }
}

@keyframes right-arm-upper {
  0% {
    top: 46%;
    transform: rotate(-20deg);
  }
  50% {
    top: 35%;
    transform: rotate(20deg);
  }
  100% {
    top: 46%;
    transform: rotate(-20deg);
  }
}

@keyframes laptop-top {
  3% {
    top: 57%;
    transform: rotate(-5deg);
  }
  49% {
    top: 57%;
    transform: rotate(0deg);
  }
  53% {
    top: 57%;
    transform: rotate(5deg);
  }
  99% {
    top: 57%;
    transform: rotate(0deg);
  }
}

@keyframes laptop-bottom {
  3% {
    top: 97%;
    transform: rotate(-5deg);
  }
  49% {
    top: 97%;
    transform: rotate(0deg);
  }
  53% {
    top: 97%;
    transform: rotate(5deg);
  }
  99% {
    top: 97%;
    transform: rotate(0deg);
  }
}
</style>
