<template>
  <div class="about">
    <div class="by-day-by-night">
      <h2> Developer by Day </h2>
      <Programmer />
      <div class="card">
        <h3> Hi! I'm Bastion! </h3>
        <ul>
          <li>
            UI Developer based out of Austin, TX
          </li>
          <li>
            Builder of communities
          </li>
          <li>
            Occasional blogger
          </li>
          <li>
            Cat dad
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import Programmer from "./Programmer";

@Component({
  components: {
    Programmer,
  }
})

export default class About extends Vue {}
</script>

<style scoped lang="less">
@import "../lib/colors.less";

.by-day-by-night {
  background: @CYAN1;
  min-height: 400px;
  padding-bottom: 30px;
  padding-top: 60px;
  position: relative;
}

.by-day-by-night::after {
  border-color: @CYAN1 transparent transparent transparent;
  border-style: solid;
  border-width: 60px 100vw 0 0;
  bottom: -60px;
  content: " ";
  display: block;
  left: 0;
  position: absolute;
}

h2 {
  font-size: 36px;
  margin: 0;
  padding-top: 20px;
  text-align: center;
}

h3 {
  font-size: 24px;
}

.card {
  background: white;
  border-radius: 8px;
  font-size: 18px;
  margin: 0 auto;
  max-width: 800px;
  min-height: 500px;
  padding: 20px;
  text-align: center;
}

ul {
  list-style-type: none;
  padding: 0;
}

</style>
