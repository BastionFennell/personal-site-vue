<template>
  <div class="dancers">
    <div class="lead">
      <div class="l-head" />
      <div class="l-right-arm-upper" />
      <div class="l-right-arm-lower" />
      <div class="l-body" />
      <div class="l-left-arm-upper" />
      <div class="l-left-arm-lower" />
    </div>
    <div class="follow">
      <div class="f-head" />
      <div class="f-right-arm-upper" />
      <div class="f-right-arm-lower" />
      <div class="f-body" />
      <div class="f-left-arm-upper" />
      <div class="f-left-arm-lower" />
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";

@Component
export default class Dancers extends Vue {}
</script>

<style scoped lang="less">
@import "../../lib/colors.less";

.dancers {
  display: flex;
  justify-content: center;
  height: 30vw;
  position: relative;
  width: 100vw;
}

.lead {
  height: 100%;
  position: relative;
  width: 40%;
}

.l-head {
  animation-duration: 2s;
  animation-iteration-count: infinite;
  animation-name: l-head;
  background-color: pink;
  border-radius: 100px;
  height: 40%;
  width: 30%;
  left: 40%;
  position: absolute;
  z-index: 5;
}

.l-body {
  animation-duration: 2s;
  animation-iteration-count: infinite;
  animation-name: l-body;
  background-color: @CYAN5;
  border-top-left-radius: 80px;
  border-top-right-radius: 80px;
  height: 70%;
  left: 31%;
  position: absolute;
  top: 25%;
  width: 40%;
  z-index: 2;
}

.l-left-arm-upper {
  animation-duration: 2s;
  animation-iteration-count: infinite;
  animation-name: l-left-arm-upper;
  background-color: @CYAN6;
  border-bottom-right-radius: 30px;
  height: 15%;
  left: 45%;
  position: absolute;
  top: 40%;
  transform: rotate(30deg);
  width: 40%;
  z-index: 1;
}

.l-left-arm-lower {
  animation-duration: 2s;
  animation-iteration-count: infinite;
  animation-name: l-left-arm-lower;
  background-color: @CYAN6;
  border-bottom-left-radius: 100px;
  border-bottom-right-radius: 100px;
  border-top-right-radius: 100px;
  height: 15%;
  left: 70%;
  position: absolute;
  top: 51%;
  transform: rotate(10deg);
  width: 34%;
  z-index: 1;
}

.l-right-arm-upper {
  animation-duration: 2s;
  animation-iteration-count: infinite;
  animation-name: l-right-arm-upper;
  background-color: @CYAN4;
  border-bottom-left-radius: 100px;
  border-bottom-right-radius: 30px;
  border-top-left-radius: 100px;
  height: 15%;
  left: 12%;
  position: absolute;
  top: 50%;
  transform: rotate(130deg);
  width: 35%;
  z-index: 6;
}

.l-right-arm-lower {
  animation-duration: 2s;
  animation-iteration-count: infinite;
  animation-name: l-right-arm-lower;
  background-color: @CYAN4;
  border-radius: 100px;
  height: 15%;
  left: 5%;
  position: absolute;
  top: 78%;
  transform: rotate(90deg);
  width: 30%;
  z-index: 6;
}

.follow {
  height: 100%;
  position: relative;
  width: 40%;
}

.f-head {
  animation-duration: 2s;
  animation-iteration-count: infinite;
  animation-name: f-head;
  background-color: pink;
  border-radius: 100px;
  height: 40%;
  width: 30%;
  left: 30%;
  position: absolute;
  z-index: 5;
}

.f-body {
  animation-duration: 2s;
  animation-iteration-count: infinite;
  animation-name: f-body;
  background-color: @GREEN5;
  border-top-left-radius: 80px;
  border-top-right-radius: 80px;
  height: 70%;
  left: 31%;
  position: absolute;
  top: 25%;
  width: 40%;
  z-index: 2;
}

.f-right-arm-upper {
  animation-duration: 2s;
  animation-iteration-count: infinite;
  animation-name: f-right-arm-upper;
  background-color: @GREEN6;
  border-bottom-left-radius: 30px;
  height: 15%;
  left: 15%;
  position: absolute;
  top: 40%;
  transform: rotate(-30deg);
  width: 40%;
  z-index: 1;
}

.f-right-arm-lower {
  animation-duration: 2s;
  animation-iteration-count: infinite;
  animation-name: f-right-arm-lower;
  background-color: @GREEN6;
  border-bottom-right-radius: 100px;
  border-bottom-left-radius: 100px;
  border-top-left-radius: 100px;
  height: 15%;
  left: -4%;
  position: absolute;
  top: 51%;
  transform: rotate(-10deg);
  width: 34%;
  z-index: 1;
}

.f-left-arm-upper {
  animation-duration: 2s;
  animation-iteration-count: infinite;
  animation-name: f-left-arm-upper;
  background-color: @GREEN4;
  border-bottom-right-radius: 100px;
  border-bottom-left-radius: 30px;
  border-top-right-radius: 100px;
  height: 15%;
  left: 55%;
  position: absolute;
  top: 50%;
  transform: rotate(-130deg);
  width: 35%;
  z-index: 6;
}

.f-left-arm-lower {
  animation-duration: 2s;
  animation-iteration-count: infinite;
  animation-name: f-left-arm-lower;
  background-color: @GREEN4;
  border-radius: 100px;
  height: 15%;
  left: 67%;
  position: absolute;
  top: 78%;
  transform: rotate(-90deg);
  width: 30%;
  z-index: 6;
}

@keyframes l-head {
  0% {
    left: 40%;
  }
  50% {
    left: 38%;
  }
  100% {
    left: 40%;
  }
}

@keyframes l-body {
  0% {
    left: 31%;
    transform: none;
  }
  50% {
    transform: rotate(5deg);
    left: 27%;
  }
  100% {
    left: 31%;
    transform: none;
  }
}

@keyframes l-left-arm-lower {
  0% {
    top: 51%;
  }
  50% {
    top: 48%;
  }
  100% {
    top: 51%;
  }
}

@keyframes l-left-arm-upper {
  0% {
    left: 45%;
    top: 40%;
    transform: rotate(30deg);
  }
  50% {
    left: 43%;
    top: 39%;
    transform: rotate(20deg);
  }
  100% {
    left: 45%;
    top: 40%;
    transform: rotate(30deg);
  }
}

@keyframes l-right-arm-upper {
  0% {
    left: 12%;
    top: 50%;
    transform: rotate(130deg);
  }
  50% {
    left: 7%;
    top: 48%;
    transform: rotate(140deg);
  }
  100% {
    left: 12%;
    top: 50%;
    transform: rotate(130deg);
  }
}

@keyframes l-right-arm-lower {
  0% {
    left: 5%;
    top: 78%;
    transform: rotate(90deg);
  }
  50% {
    left: -1%;
    top: 74%;
    transform: rotate(80deg);
  }
  100% {
    left: 5%;
    top: 78%;
    transform: rotate(90deg);
  }
}

@keyframes f-head {
  0% {
    left: 30%;
  }
  50% {
    left: 32%;
  }
  100% {
    left: 30%;
  }
}

@keyframes f-body {
  0% {
    left: 31%;
    transform: none;
  }
  50% {
    transform: rotate(-5deg);
    left: 35%;
  }
  100% {
    left: 31%;
    transform: none;
  }
}

@keyframes f-right-arm-lower {
  0% {
    top: 51%;
  }
  50% {
    top: 48%;
  }
  100% {
    top: 51%;
  }
}

@keyframes f-right-arm-upper {
  0% {
    left: 15%;
    top: 40%;
    transform: rotate(-30deg);
  }
  50% {
    left: 17%;
    top: 39%;
    transform: rotate(-20deg);
  }
  100% {
    left: 15%;
    top: 40%;
    transform: rotate(-30deg);
  }
}

@keyframes f-left-arm-upper {
  0% {
    left: 55%;
    top: 50%;
    transform: rotate(-130deg);
  }
  50% {
    left: 60%;
    top: 48%;
    transform: rotate(-140deg);
  }
  100% {
    left: 55%;
    top: 50%;
    transform: rotate(-130deg);
  }
}

@keyframes f-left-arm-lower {
  0% {
    left: 67%;
    top: 78%;
    transform: rotate(-90deg);
  }
  50% {
    left: 73%;
    top: 74%;
    transform: rotate(-80deg);
  }
  100% {
    left: 67%;
    top: 78%;
    transform: rotate(-90deg);
  }
}
</style>
