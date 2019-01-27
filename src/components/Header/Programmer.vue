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
  display: flex;
  height: 15vw;
  justify-content: center;
  position: relative;
  width: 50vw;
}

.head {
  background-color: pink;
  border-radius: 100px;
  height: 40%;
  left: 45%;
  position: absolute;
  top: 10%;
  width: 12%;
  z-index: 2;
}

.body {
  background-color: @CYAN5;
  border-top-left-radius: 80px;
  border-top-right-radius: 80px;
  height: 70%;
  left: 41%;
  position: absolute;
  top: 30%;
  width: 20%;
  z-index: 1;
}

.right-arm-upper {
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
  background-color: @CYAN6;
  border-radius: 100px;
  height: 20%;
  left: 32%;
  position: absolute;
  top: 57%;
  transform: rotate(20deg);
  width: 15%;
  z-index: 2;
}

.left-arm-upper {
  background-color: @CYAN6;
  border-radius: 100px;
  height: 20%;
  left: 55%;
  position: absolute;
  top: 46%;
  transform: rotate(20deg);
  width: 15%;
  z-index: 2;
}

.left-arm-lower {
  background-color: @CYAN6;
  border-radius: 100px;
  height: 20%;
  left: 55%;
  position: absolute;
  top: 57%;
  transform: rotate(-20deg);
  width: 15%;
  z-index: 2;
}

.laptop-top {
  background-color: @GRAY6;
  border-radius: 6px;
  left: 41%;
  width: 20%;
  height: 40%;
  position: absolute;
  top: 57%;
  z-index: 3;
}

.laptop-bottom {
  background-color: @GRAY6;
  left: 41%;
  width: 20%;
  height: 3%;
  position: absolute;
  top: 97%;
  z-index: 3;
}

.laptop-logo {
  background-color: @GREEN5;
  left: 49%;
  top: 70%;
  border-radius: 100px;
  height: 16%;
  position: absolute;
  width: 5%;
  z-index: 4;
}

</style>
