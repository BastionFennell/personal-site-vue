<template>
  <button
    class="light-switch"
    v-bind:class="{ 'is-day': isDay }"
    role="switch"
    v-bind:aria-checked="isDay ? 'true' : 'false'"
    v-on:click="onToggle"
  >
    <div class="light-switch__slide" v-bind:class="{ 'is-day': isDay }">
      <div class="light-switch__side day">
        <h2 v-bind:class="{ 'is-day': isDay }">Day</h2>
      </div>
      <div
        class="light-switch__toggle-ball"
        v-bind:class="{ 'is-day': isDay }"
      />
      <div class="light-switch__side night">
        <h2 v-bind:class="{ 'is-day': isDay }">Night</h2>
      </div>
    </div>
  </button>
</template>

<script lang="ts">
import { Component, Prop, Vue } from "vue-property-decorator";
import Programmer from "./Programmer.vue";
import Blog from "@/components/Blog";

@Component({})
export default class About extends Vue {
  @Prop() isDay!: boolean;
  @Prop() onToggle!: Function;
}
</script>

<style scoped lang="less">
@import "../../lib/colors.less";

h2 {
  font-size: 36px;
  margin: 0;
}

.light-switch {
  background: @CYAN7;
  border: none;
  border-radius: 150px;
  display: block;
  font-family: inherit;
  font-size: inherit;
  font-weight: inherit;
  height: 100px;
  margin: 0 auto;
  min-width: 300px;
  max-width: 800px;
  outline: none;
  padding: 0;
  position: relative;
  transition: background 0.3s ease;

  &.is-day {
    background: @CYAN5;
  }
}

.light-switch__slide {
  display: flex;
  left: calc(-100% - 50px);
  width: calc(200% + 100px);
  position: relative;
  transition: left 0.3s ease;

  &.is-day {
    left: -150px;
  }
}

.light-switch__toggle-ball {
  height: 100px;
  width: 100px;
  background: @GRAY2;
  border-radius: 50%;
  flex-shrink: 0;
  position: relative;
  transition: all 0.3s ease;

  &.is-day {
    background: hsl(43, 90%, 76%);
  }
}

.light-switch__side {
  flex-shrink: 0;
  overflow: hidden;
  position: relative;
  width: 50%;

  h2 {
    position: absolute;
    left: 0;
    width: 100%;
    top: calc(50% - 25px);
  }

  &.night h2 {
    color: @GRAY2;
    left: -50px;
    transition: left 0.3s ease;

    &.is-day {
      left: calc(-100% + 100px);
    }
  }

  &.day h2 {
    left: calc(100% - 100px);
    transition: left 0.3s ease;

    &.is-day {
      left: 50px;
    }
  }
}
</style>
