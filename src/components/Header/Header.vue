<template>
  <div class="header">
    <BastionTheX class="bastion-the-x" />
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import BastionTheX from "./BastionTheX.vue";
import Dancers from "./Dancers.vue";
import Programmer from "./Programmer.vue";

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
  text-align: center;
}

.header::after {
  border-color: transparent white transparent transparent;
  border-style: solid;
  border-width: 0 100vw 60px 0;
  bottom: -60px;
  content: " ";
  display: block;
  left: 0;
  position: absolute;
  z-index: 1;
}

</style>

