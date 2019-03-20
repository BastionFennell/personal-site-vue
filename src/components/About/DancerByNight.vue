<template>
  <div class="dancer-by-night">
      <Dancers class="dancer-by-night__dancers" />
      <div class="card">
        <h3>Hi! I'm Bastion!</h3>
        <p>
          I'm a <strong>West Coast Swing</strong> dancer and
          teacher based out of <strong>Austin, TX</strong>. I
          dance competitively all around the US in the
          <strong>Advanced</strong> division, the second highest
          competitive division.
        </p>
        <p>
          As a dancer, I believe it's crucial to give back and
          support the community that has given me so much and
          made my evenings much more enjoyable. I support the
          local community through <strong>teaching</strong> both
          <strong>private lessons</strong> and a weekly
          <strong>group class</strong>.
        </p>
        <p>
          I also have a yearly weekend long event called
          <strong>Monster Mayhem</strong> that was put together
          to help grow the community. For this event, we fly in
          out of state pros and put together a weekend full of
          workshops for the local community. In 2019, our event
          brought in around <strong>100 participants</strong>.
        </p>
        <p class="card__label">
          Some of the things I did for this event were:
        </p>
        <ul>
          <li>Handle marketing both at other events and via social media</li>
          <li>Coordinate with pros, studios, and other events</li>
          <li>Negotiate mutually beneficial contracts</li>
          <li>Not sleeping a wink during the event</li>
          <li>Design and build the event website</li>
          <li>MCing throughout the weekend</li>
        </ul>
      </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import Dancers from "./Dancers.vue";

@Component({
  components: {
    Dancers
  }
})
export default class DancerByNight extends Vue {}
</script>

<style scoped lang="less">
@import "../../lib/colors.less";

strong {
  border-bottom: 1px dashed hsl(360, 67%, 44%);
  color: hsl(42, 78%, 60%);
}

h2 {
  font-size: 36px;
  margin: 0;
  text-align: center;
}

h3 {
  font-size: 24px;
}

ul {
  list-style-type: none;
  margin-top: 10px;
  padding: 0;
  text-align: center;
}

li {
  padding: 3px 0;
}

.dancer-by-night {
  min-height: 400px;
  padding-bottom: 30px;
  padding-top: 60px;
  position: relative;
  z-index: 2;
}

.dancer-by-night__dancers {
  max-width: 800px;
  max-height: 240px;
  margin: 0 auto;
}

.card {
  background: transparent;
  border-radius: 8px;
  font-size: 18px;
  margin: 0 auto;
  max-width: 800px;
  min-height: 500px;
  padding: 20px;
}

@media (min-width: 700px) {
  .card {
    background: white;
  }
}

.card__label {
  margin-bottom: 0;
  margin-top: 2em;
  text-align: center;
}


</style>
