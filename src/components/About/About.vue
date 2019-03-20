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
    <div class="contact">
      <h3>How can you get in touch?</h3>
      <div class="contact__icons">
        <a href="https://twitter.com/bastionthedev">
          <i class="fab fa-twitter-square"></i>
        </a>
        <a href="https://github.com/bastionfennell">
          <i class="fab fa-github-square"></i>
        </a>
        <a href="mailto:bastion@bastionthe.dev">
          <i class="fas fa-envelope-square"></i>
        </a>
        <a href="https://dev.to/bastionthedev">
          <i class="fab fa-dev"></i>
        </a>
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

.contact {
  background: @CYAN8;
  color: white;
  padding-bottom: 100px;
  padding-top: 40px;
  position: relative;

  h3 {
    font-size: 24px;
    margin: 0;
    text-align: center;
  }

  &::before {
    border-color: transparent transparent @CYAN8 transparent;
    border-style: solid;
    border-width: 0 0 60px 100vw;
    top: -59px;
    content: " ";
    display: block;
    left: 0;
    position: absolute;
  }
}

.contact__icons {
  align-items: center;
  display: flex;
  justify-content: space-around;
  margin: 30px auto;
  max-width: 800px;

  a {
    color: white;
    text-decoration: none !important;
    transition: color 0.4s ease;

    &:hover {
      color: @CYAN3;
    }
  }

  i {
    font-size: 60px;
  }
}

</style>
