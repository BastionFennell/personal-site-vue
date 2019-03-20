<template>
  <div class="container">
    <div class="dev-by-day" v-bind:class="{ day: isDay }">
      <Programmer class="dev-by-day__programmer" />
      <div class="card">
        <h3>Hi! I'm Bastion!</h3>
        <p>
          I'm a <strong>UI Developer</strong> based out of
          <strong>Austin, TX</strong>. my focus is developing
          <strong>software for humans</strong>, both the end users and other
          programmers in my projects.
        </p>
        <p>
          As a lead, I aim to build a team that is
          <strong>Radically Candid</strong>. A team that not only
          <strong>executes</strong>, but one that continues to
          <strong>learn</strong> and <strong>grow</strong>. I think of myself as
          a <strong>big band developer</strong> rather than a rock star, part of
          a team that works well together and ships quality software.
        </p>
        <p class="card__label">
          I also think of myself as a:
        </p>
        <ul>
          <li>
            Builder of communities
          </li>
          <li>
            Reluctant weightlifter
          </li>
          <li>
            Occasional blogger
          </li>
          <li>
            Mentor and coach
          </li>
          <li>
            Vim advocate
          </li>
          <li>
            Cat dad
          </li>
        </ul>
      </div>
    </div>
    <div class="portfolio">
      <h3>What have I done recently?</h3>
      <div class="portfolio__grid">
        <div class="portfolio__card">
          <div class="portfolio__card-picture">
            <img src="./monster-mayhem.png" alt="Monster Mayhem WCS" />
          </div>
          <div class="portfolio__card-summary">
            <h4>Monster Mayhem</h4>
            <p>
              A weekend long dance event that I built and organize. I
              <strong>designed the layout</strong> of the site, built the site
              using <strong>react.js</strong>, and deployed the site using
              Amazon <strong>S3</strong> and <strong>Cloudfront</strong>. I also
              handled the social media and marketing for the event.
            </p>
            <a href="https://monstermayhem.dance">
              <button class="portfolio__see-more">
                View Project
                <i class="fas fa-angle-right"></i>
              </button>
            </a>
          </div>
        </div>
        <div class="portfolio__card">
          <div class="portfolio__card-picture">
            <img src="./clicker.gif" alt="Code Clicker" />
          </div>
          <div class="portfolio__card-summary">
            <h4>Code Clicker</h4>
            <p>
              A small clicker game in vanilla js. I
              <strong>mentored</strong> two developers as they built the initial
              game, then used what we built as the basis for a series of
              <strong>blog posts</strong> that aimed to introduce new developers
              to <strong>HTML</strong>, <strong>CSS</strong>, and
              <strong>vanilla javascript</strong>.
            </p>
          </div>
        </div>
      </div>
    </div>
    <Blog class="dev-by-day__blog" />
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from "vue-property-decorator";
import Programmer from "./Programmer.vue";
import LightSwitch from "./LightSwitch.vue";
import Blog from "@/components/Blog";

@Component({
  components: {
    Blog,
    LightSwitch,
    Programmer
  }
})
export default class DevByDay extends Vue {
  @Prop() isDay!: boolean;
}
</script>

<style scoped lang="less">
@import "../../lib/colors.less";

.container {
  background: @CYAN3;
  display: flex;
  flex-direction: column;
}

.dev-by-day__programmer {
  max-width: 800px;
  max-height: 240px;
  margin: 0 auto;
}

.dev-by-day {
  background: @CYAN9;
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

.dev-by-day::after {
  border-color: @CYAN1 transparent transparent transparent;
  border-style: solid;
  border-width: 60px 100vw 0 0;
  bottom: -60px;
  content: " ";
  display: block;
  left: 0;
  overflow-x: hidden;
  position: absolute;
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

strong {
  border-bottom: 1px dashed hsl(360, 67%, 44%);
  color: hsl(42, 78%, 60%);
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

.portfolio {
  background: white;
  font-size: 18px;
  padding-bottom: 80px;
  padding-top: 80px;
  position: relative;
  z-index: 1;

  h3 {
    text-align: center;
  }

  &::after {
    border-color: white transparent transparent transparent;
    border-style: solid;
    border-width: 60px 100vw 0 0;
    bottom: -60px;
    content: " ";
    display: block;
    left: 0;
    overflow-x: hidden;
    position: absolute;
  }
}

.portfolio__grid {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-evenly;
  margin: 0 auto;
  max-width: 400px;
  padding: 0 15px;

  a {
    color: inherit !important;
    text-decoration: none !important;
  }
}

.portfolio__card {
  border: 1px solid black;
  border-radius: 8px;
  box-sizing: border-box;
  flex-shrink: 0;
  height: 350px;
  margin: 20px 15px 10px 15px;
  overflow: hidden;
  position: relative;
  width: 350px;
}

@media (min-width: 700px) {
  .portfolio__grid {
    max-width: 800px;
  }
}

.portfolio__card-picture {
  img {
    height: 100%;
    width: 100%;
  }
}

.portfolio__card-summary {
  background-color: @CYAN9;
  color: white;
  box-sizing: border-box;
  height: 100%;
  opacity: 0;
  padding: 20px 30px;
  position: absolute;
  top: 0;
  transition: opacity 0.3s ease;
  width: 100%;
  visibility: none;

  a {
    display: block;
    height: 0;
    overflow: hidden;
    pointer-events: none;
    text-align: center;
  }

  &:hover {
    opacity: 0.9;

    a {
      animation-delay: 0.1s;
      animation-duration: 0.1s;
      animation-fill-mode: forwards;
      animation-name: anchor;
      height: auto;
    }
  }

  h4 {
    margin-top: 5px;
    text-align: center;
  }
}

.portfolio__see-more {
  background: transparent;
  border: 2px solid @CYAN6;
  border-radius: 8px;
  color: white;
  font-size: 1em;
  text-align: center;
  transition: all 0.2s ease;
  padding: 10px 10px;

  i {
    font-size: 22px;
    margin-top: -2px;
    margin-left: 5px;
    position: relative;
    top: 3px;
  }

  &:hover {
    background-color: @CYAN6;
    cursor: pointer;
  }
}

.dev-by-day__blog {
  flex-grow: 1;
}

@keyframes anchor {
  0% {
    pointer-events: none;
  }
  100% {
    pointer-events: initial;
  }
}
</style>
