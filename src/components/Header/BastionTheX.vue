<template>
  <div class="bastion-the-x">
    <div class="title-text">
      <h1>Bastion The<span class="name">{{ name }}</span></h1>
      <div v-bind:style="cursorStyle" />
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";

const NAMES = [
  "Dev",
  "Dancer",
  "Great",
  "Alright",
  "Friend",
  "Foe",
  "Student",
  "Mentor",
  "Programmer",
  "Director",
  "User",
  "Roleplayer",
  "Reviewer",
  "Lead"
];

const REFRESH_RATE = 1500;

function getRandomNumber(num: number): number {
  return Math.floor(Math.random() * num);
}

@Component
export default class BastionTheX extends Vue {
  blinkTimer: any = "";
  fullName: string = NAMES[0];
  name: string = NAMES[0];
  showCursor: boolean = true;
  creating: boolean = false;
  updating: boolean = false;

  get cursorStyle(): object {
    return {
      background: this.updating || this.showCursor ? "black" : "none",
      height: "80%",
      width: "1px",
      boxSizing: "borderBox"
    };
  }

  created(): void {
    this.blinkTimer = setInterval(this.blinkCursor, 400);
    setTimeout(this.deleteName, REFRESH_RATE);
  }

  blinkCursor(): void {
    this.showCursor = !this.showCursor;
  }

  addName(): void {
    if (this.name.length === this.fullName.length) {
      this.scheduleUpdate();
      return;
    }

    this.updating = true;
    this.name = this.fullName.slice(0, this.name.length + 1);
    const randomOffset = getRandomNumber(100);
    setTimeout(this.addName, 200 - randomOffset);
  }

  deleteName(): void {
    if (this.name.length === 0) {
      this.scheduleUpdate();
      return;
    }

    this.updating = true;
    this.name = this.name.slice(0, -1);
    const randomOffset = getRandomNumber(50);
    setTimeout(this.deleteName, 100 - randomOffset);
  }

  scheduleUpdate(): void {
    this.updating = false;

    if (this.creating) {
      setTimeout(this.deleteName, REFRESH_RATE);
    } else {
      this.fullName = this.getNewName();
      setTimeout(this.addName, REFRESH_RATE);
    }

    this.creating = !this.creating;
  }

  getNewName(): string {
    let newName: string = this.fullName;

    while(newName === this.fullName) {
      newName = NAMES[getRandomNumber(NAMES.length)];
    }

    return newName;
  }

  destroyed(): void {
    clearInterval(this.blinkTimer);
  }
}
</script>

<style scoped lang="less">
@import "../../lib/colors.less";

.bastion-the-x {
  display: flex;
  flex-direction: row;
  justify-content: space-around;
}

.title-text {
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  align-items: center;
}

h1 {
  margin: 0;
}

.name {
  color: @CYAN8;
  margin-left: 10px;
}
</style>
