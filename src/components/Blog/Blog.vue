<template>
  <div class="blog">
    <h3> What do I Think About Things? </h3>
    <div class="blog__post-list">
      <div v-for="post in posts">
        <BlogCard class="blog__post" v-bind:post="post" />
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import BlogCard from './BlogCard.vue';
import posts from "./posts.json";

@Component({
  components: {
    BlogCard
  }
})

export default class Blog extends Vue {
  data() {
    return { posts };
  }
}
</script>

<style scoped lang="less">
@import "../../lib/colors.less";

h3 {
  font-size: 24px;
  text-align: center;
}

.blog {
  background: @CYAN3;
  padding-bottom: 100px;
  padding-top: 100px;
}

.blog__post {
  margin: 20px auto;
}

</style>
