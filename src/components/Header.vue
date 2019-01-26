<template>
  <div class="header">
    <BastionTheX class="bastion-the-x" />
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
@import "../lib/colors.less";

.bastion-the-x {
  padding-top: 100px;
}

.header {
  height: 100vh;
}
</style>
