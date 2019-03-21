<template>
  <div class="container">
    <div class="dancer-by-night" v-bind:class="{ day: isDay }">
      <Dancers class="dancer-by-night__dancers" />
      <div class="card">
        <h3>Hi! I'm Bastion!</h3>
        <p>
          I'm a <strong>West Coast Swing</strong> dancer and teacher based out
          of <strong>Austin, TX</strong>. I dance competitively all around the
          US in the <strong>Advanced</strong> division, the second highest
          competitive division.
        </p>
        <p>
          As a dancer, I believe it's crucial to give back and support the
          community that has given me so much and made my evenings much more
          enjoyable. I support the local community through
          <strong>teaching</strong> both <strong>private lessons</strong> and a
          weekly <strong>group class</strong>.
        </p>
        <p>
          I also have a yearly weekend long event called
          <strong>Monster Mayhem</strong> that was put together to help grow the
          community. For this event, we fly in out of state pros and put
          together a weekend full of workshops for the local community. In 2019,
          our event brought in around <strong>100 participants</strong>.
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
    <div class="west-coast-swing">
      <div class="west-coast-swing__text">
        <h3>What is West Coast Swing?</h3>
        <p>
          West Coast Swing is a partner dance based heavily on Lindy Hop. It
          gets its unique look and feel from the elastic connection and the
          fact that it's a slotted dance, like salsa.
        </p>
        <p>
          Most importantly for me, WCS is a social dance. It relies on
          lead-follow rather than choreography, so you can dance with anyone.
          Even the competitions are lead-follow. Due to its social nature, the
          dance has also grown and evolved with modern music and dancing trends.
          We dance to everything from blues music to top 40s!
        </p>
        <p>
          I started competing in West Coast Swing after trying competitive
          country dancing. Aside from it just being cheaper for a college
          student like I was, what made me fall in love with the dance was the
          community. Everyone is welcoming, we all dance with each other and
          hang out at the big competitions. This dance has given me the chance
          to make incredible friends all over the world!
        </p>
      </div>
    </div>
    <div class="videos">
      <h3>What does my dancing look like?</h3>
      <div class="videos__list">
        <div class="videos__video">
          <iframe
            src="https://www.youtube.com/embed/1PNnLQCaTpY"
            frameborder="0"
            allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture"
            allowfullscreen
          ></iframe>
        </div>
        <div class="videos__video">
          <iframe
            src="https://www.youtube.com/embed/qI7JUq3vNYk"
            frameborder="0"
            allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture"
            allowfullscree
          ></iframe>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from "vue-property-decorator";
import Dancers from "./Dancers.vue";

@Component({
  components: {
    Dancers
  }
})
export default class DancerByNight extends Vue {
  @Prop() isDay!: boolean;
}
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
  text-align: center;
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

.container {
  background: @CYAN7;
  display: flex;
  flex-direction: column;
}

.dancer-by-night {
  background: @CYAN9;
  font-size: 18px;
  min-height: 400px;
  padding-bottom: 30px;
  padding-top: 60px;
  position: relative;
  transition: background 0.3s ease;
  z-index: 2;

  &.day {
    background: @CYAN1;
  }
}

.dancer-by-night::after {
  border-color: @CYAN9 transparent transparent transparent;
  border-style: solid;
  border-width: 60px 100vw 0 0;
  bottom: -59px;
  content: " ";
  display: block;
  left: 0;
  overflow-x: hidden;
  position: absolute;
}

.dancer-by-night__dancers {
  max-width: 800px;
  max-height: 240px;
  margin: 0 auto;
}

.card {
  background: transparent;
  border-radius: 8px;
  color: white;
  margin: 0 auto;
  max-width: 800px;
  min-height: 500px;
  padding: 20px;
}

@media (min-width: 700px) {
  .card {
    background: white;
    color: inherit;
  }
}

.card__label {
  margin-bottom: 0;
  margin-top: 2em;
  text-align: center;
}

.west-coast-swing {
  background: @GRAY8;
  color: white;
  font-size: 18px;
  padding: 80px 20px;
  position: relative;

  &::after {
    border-color: @GRAY8 transparent transparent transparent;
    border-style: solid;
    border-width: 60px 100vw 0 0;
    bottom: -59px;
    content: " ";
    display: block;
    left: 0;
    overflow-x: hidden;
    position: absolute;
  }
}

.west-coast-swing__text {
  margin: 0 auto;
  max-width: 800px;
  z-index: 1;
}

.videos {
  flex-direction: column;
  display: flex;
  background: @CYAN7;
  color: white;
  flex-grow: 1;
  padding-top: 80px;
}

.videos__list {
  box-sizing: border-box;
  display: flex;
  flex-direction: column;
  flex-grow: 1;
  justify-content: space-evenly;
  margin: 0 auto;
  max-width: 800px;
  padding: 0 20px 20px 20px;
  width: 100%;
}

.videos__video {
  position: relative;
  width: 100%;
  height: 0;
  padding-bottom: 56.25%;
  margin: 40px 0;

  iframe {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
  }
}
</style>
