<template>
  <div class="header">
    <BastionTheX class="bastion-the-x" />
    <div class="subheaders">
      <h2> Frontend Dev by Day </h2>
      <h2> Dancer by Night </h2>
    </div>
    <div class="animations">
      <Programmer />
      <div class="separator" />
      <Dancers />
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import BastionTheX from "./BastionTheX.vue";
import Dancers from "./Dancers.vue";
import Programmer from "./Programmer.vue";

@Component({
  components: {
    BastionTheX,
    Dancers,
    Programmer
  }
})
export default class Header extends Vue {}
</script>

<style scoped lang="less">
@import "../../lib/colors.less";

.bastion-the-x {
  padding: 100px 0;
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

.subheaders {
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  padding-bottom: 20px;
}

.animations {
  display: flex;
  flex-direction: row;
  justify-content: center;
}

.separator {
  width: 1px;
  height: 15vw;
  background: @GRAY9;
}
</style>
