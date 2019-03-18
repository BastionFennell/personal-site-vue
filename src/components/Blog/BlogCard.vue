<template>
  <div class="blog-card">
    <div class="blog-card__main">
      <h4>
        {{post.title}}
      </h4>
      <div class="blog-card__tags">
        <div v-for="tag in post.tags">
          <div class="blog-card__tag">
            {{tag}}
          </div>
        </div>
      </div>
      <div class="blog-card__description">
        {{post.description}}
      </div>
      <div class="blog-card__time-to-read">
        {{post.timeToRead}} read
      </div>
    </div>
    <div class="blog-card__secondary">
      <div class="blog-card__date">
        {{post.date}}
      </div>
      <a v-bind:href="post.link">
        <button class="blog-card__see-more">
          View Post
        </button>
      </a>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from "vue-property-decorator";

@Component()
export default class BlogPost extends Vue {
  @Prop() post!: Array;
}

</script>

<style scoped lang="less">
@import "../../lib/colors.less";

h4 {
  font-size: 20px;
  margin-bottom: 5px;
  margin-top: 0;
}

.blog-card {
  background: white;
  border-radius: 8px;
  display: flex;
  max-width: 800px;
  padding: 20px;
}
.blog-card__main {
  align-items: flex-start;
  display: flex;
  flex-direction: column;
  flex-grow: 1;
  justify-content: space-between;

}

.blog-card__secondary {
  align-items: flex-end;
  display: flex;
  flex-direction: column;
  flex-shrink: 0;
  justify-content: space-between;
  padding-left: 15px;
}

.blog-card__tags {
  display: flex;
  margin-bottom: 10px;
}

.blog-card__tag {
  background: @GREEN3;
  border-radius: 8px;
  padding: 5px 10px;
  margin-right: 10px;
}

.blog-card__description {
  margin-bottom: 10px;
}

.blog-card__time-to-read {
  color: @GRAY6;
}

.blog-card__see-more {
  background: @CYAN4;
  border: 2px solid @CYAN4;
  border-radius: 8px;
  color: white;
  font-size: 1em;
  text-align: center;
  transition: background 0.2s ease;
  outline: none;
  padding: 10px 10px;

  &:hover {
    background: @CYAN6;
    border-color: @CYAN6;
    cursor: pointer;
  }
}

</style>
