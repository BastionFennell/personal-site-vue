<template>
  <div class="about">
      <LightSwitch
        class="light-switch"
        v-bind:isDay="isDay"
        v-bind:onToggle="toggleDay"
        />
      <DevByDay v-if="isDay" />
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import DevByDay from "./DevByDay.vue";
import Programmer from "./Programmer.vue";
import LightSwitch from "./LightSwitch.vue";
import Blog from "@/components/Blog";

@Component({
  components: {
    DevByDay,
    LightSwitch,
  },
  data: function() {
    return {
      isDay: true
    }
  },
  methods: {
    toggleDay: function() {
      this.isDay = !this.isDay;
    }
  }
})
export default class About extends Vue {}
</script>

<style scoped lang="less">
@import "../../lib/colors.less";

.about {
  background: @CYAN1;
  padding-top: 100px;
}

</style>
