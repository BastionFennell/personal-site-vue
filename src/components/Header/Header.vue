<template>
  <div class="header">
    <BastionTheX class="bastion-the-x" />
    <h2> Frontend dev by day, dancer by night</h2>
    <Dancers />
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import BastionTheX from "./BastionTheX.vue";
import Dancers from "./Dancers.vue";

@Component({
  components: {
    BastionTheX,
    Dancers
  }
})
export default class Header extends Vue {}
</script>

<style scoped lang="less">
@import "../../lib/colors.less";

.bastion-the-x {
  padding-top: 100px;
}

.header {
  background: white;
  height: 100vh;
  text-align: center;
}

h2 {
  color: @GRAY7;
  font-size: 1.4em;
}
</style>
