<template>
  <div
    class="about"
    v-bind:class="{day: isDay}"
    >
      <LightSwitch
        class="light-switch"
        v-bind:isDay="isDay"
        v-bind:onToggle="toggleDay"
        />
      <div class="about__slider" v-bind:class="{day: isDay}" >
        <DevByDay class="about__dev-by-day" />
        <DancerByNight class="about__dancer-by-night" />
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import DevByDay from "./DevByDay.vue";
import DancerByNight from "./DancerByNight.vue";
import Programmer from "./Programmer.vue";
import LightSwitch from "./LightSwitch.vue";
import Blog from "@/components/Blog";

@Component({
  components: {
    DancerByNight,
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
  background: @CYAN9;
  padding-top: 100px;
  overflow: hidden;
  position: relative;
  transition: background 0.3s ease;

  &.day {
    background: @CYAN1;
  }
}

.about__slider {
  transition: left 0.3s ease;
  display: flex;
  width: 200%;
  left: -100%;
  position: relative;

  &.day {
    left: 0;
  }
}

.about__dancer-by-night {
  flex-shrink: 0;
  width: 50%;
}

.about__dev-by-day {
  flex-shrink: 0;
  width: 50%;
}
</style>
