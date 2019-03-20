<template>
  <div class="blog-card">
    <div class="blog-card__main">
      <h4>
        {{ post.title }}
      </h4>
      <div class="blog-card__tags">
        <div v-for="tag in post.tags" :key="tag">
          <div class="blog-card__tag">
            {{ tag }}
          </div>
        </div>
      </div>
      <div class="blog-card__description">
        {{ post.description }}
      </div>
      <div class="blog-card__time-to-read">
        <div class="blog-card__time-to-read-text">
          {{ post.timeToRead }} read
        </div>
        <a v-bind:href="post.link">
          <button class="blog-card__see-more small">
            View Post
          </button>
        </a>
      </div>
    </div>
    <div class="blog-card__secondary">
      <div class="blog-card__date">
        {{ post.date }}
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

@Component({})
export default class BlogPost extends Vue {
  @Prop() post!: Array<Object>;
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
  font-size: 18px;
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

@media (max-width: 600px) {
  .blog-card__secondary {
    display: none;
  }
}

.blog-card__tags {
  display: flex;
  flex-wrap: wrap;
  margin-bottom: 5px;
}

.blog-card__tag {
  background: @GREEN3;
  border-radius: 8px;
  padding: 5px 10px;
  margin-right: 10px;
  margin-bottom: 5px;
}

.blog-card__description {
  margin-bottom: 10px;
}

@media (max-width: 600px) {
  .blog-card__description {
    display: none;
  }
}

.blog-card__time-to-read {
  color: @GRAY6;
  align-items: flex-end;
  display: flex;
  justify-content: space-between;
  width: 100%;
}

@media (max-width: 400px) {
  .blog-card__time-to-read {
    align-items: flex-start;
    flex-direction: column;
  }

  .blog-card__time-to-read-text {
    margin-bottom: 5px;
  }
}

.blog-card__see-more {
  background: @CYAN4;
  border: 2px solid @CYAN4;
  border-radius: 8px;
  color: white;
  font-size: 1em;
  text-align: center;
  transition: all 0.2s ease;
  outline: none;
  padding: 10px 10px;

  &.small {
    display: none;
  }

  &:hover {
    background: @CYAN6;
    border-color: @CYAN6;
    cursor: pointer;
  }
}

@media (max-width: 600px) {
  .blog-card__see-more.small {
    display: inline-block;
  }
}
</style>
