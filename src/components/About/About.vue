<template>
  <div class="about">
    <div class="by-day-by-night">
      <h2> Developer by Day </h2>
      <Programmer />
      <div class="card">
        <h3> Hi! I'm Bastion! </h3>
        <p> I'm a <strong>UI Lead</strong> based out of <strong>Austin, TX</strong>.
          My focus is developing <strong>software for humans</strong>, both the end users and other programmers in my projects.
        </p>
        <p>
          As a lead, I aim to build a team that is <strong>Radically Candid</strong>.
          A team that not only <strong>executes</strong>, but one that continues to <strong>learn</strong> and <strong>grow</strong>.
          I think of myself as a <strong>big band developer</strong> rather than a rock star, part of a team that works well together and ships quality software.
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
      <h3> What have I done so far? </h3>
      <div class="portfolio__grid">
        <a href="https://monstermayhem.dance">
          <div class="portfolio__card">
            <div class="portfolio__card-picture">
              <img src="./monster-mayhem.png" alt="Monster Mayhem WCS"/>
            </div>
            <div class="portfolio__card-summary">
              <h4> Monster Mayhem West Coast Swing </h4>
              <p>
                A weekend long dance event that I built and organize.
                I <strong>designed the layout</strong> of the site,
                built the site using <strong>React.js</strong>,
                and deployed the site using Amazon <strong>S3</strong> and <strong>Cloudfront</strong>.
                I also handled the social media presence and marketing for the event.
              </p>
            </div>
          </div>
        </a>
        <div class="portfolio__card">
          <div class="portfolio__card-picture">
            <img src="./clicker.gif" alt="Code Clicker"/>
          </div>
          <div class="portfolio__card-summary">
            <h4> Code Clicker </h4>
            <p> A small clicker game in vanilla JS.
              I <strong>mentored</strong> two developers as they built the initial game,
              then used what we built as the basis for a series of <strong>blog posts</strong> that
              aimed to introduce new developers to <strong>HTML</strong>, <strong>CSS</strong>, and <strong>vanilla Javascript</strong>.
            </p>
          </div>
        </div>
      </div>
    </div>
    <div class="contact">
      <h3> How can you get in touch? </h3>
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
import Programmer from "./Programmer.vue";

@Component({
  components: {
    Programmer,
  }
})

export default class About extends Vue {}
</script>

<style scoped lang="less">
@import "../../lib/colors.less";

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
  overflow-x: hidden;
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
  background: transparent;
  border-radius: 8px;
  font-size: 18px;
  margin: 0 auto;
  max-width: 800px;
  min-height: 500px;
  padding: 20px;
  text-align: center;
}

@media (min-width: 700px) {
  .card {
    background: white;
  }
}

.card__label {
  margin-bottom: 0;
  margin-top: 2em;
}

strong {
  border-bottom: 1px dashed hsl(360, 67%, 44%);
  color: hsl(42, 78%, 60%);
}

ul {
  list-style-type: none;
  margin-top: 10px;
  padding: 0;
}

li {
  padding: 3px 0;
}

.portfolio {
  background: white;
  font-size: 18px;
  padding-bottom: 80px;
  padding-top: 80px;

  h3 {
    text-align: center;
  }
}

.portfolio__grid {
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
  display: flex;
  flex-direction: column;
  margin: 20px 0 10px 0;
  overflow: hidden;
  transition: all 0.3s ease;
  width: 100%;

  &:hover {
    box-shadow:0px 1px 8px 0px rgba(0, 0, 0, 0.2),
    0px 3px 4px 0px rgba(0, 0, 0, 0.14),
    0px 3px 3px -2px rgba(0, 0, 0, 0.12);
  }
}

@media (min-width: 700px) {
  .portfolio__grid {
    max-width: 800px;
  }

  .portfolio__card {
    flex-direction: row !important;
    height: 250px;
  }
}

.portfolio__card-picture {
  flex: 1;

  img {
    height: 100%;
    width: 100%;
  }
}

.portfolio__card-summary {
  flex: 1;
  padding: 10px;
  h4 {
    margin-top: 5px;
  }
}

.contact {
  background: @CYAN8;
  color: white;
  padding-bottom: 100px;
  padding-top: 40px;
  position: relative;

  h3 {
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
