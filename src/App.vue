<template>
  <div class="app">
    <post-form-vue @createPost="createPost" />
    <post-list-vue :posts="posts" @deletePost="deletePost" />
  </div>
</template>

<script>
import PostListVue from "./components/PostList.vue";
import PostFormVue from "./components/PostForm.vue";

export default {
  components: {
    PostListVue,
    PostFormVue
  },
  data() {
    return {
      posts: [
        { id: 1, title: 'Vue', desc: "Описание поста о Vue" },
        { id: 2, title: 'Angular', desc: "Описание поста об Angular" },
        { id: 3, title: 'React', desc: "Описание поста о React" },
        { id: 4, title: 'JavaScript', desc: "Описание поста о JavaScript" },
      ],

    }
  },
  methods: {

    createPost(post) {
      this.posts.unshift(post);
    },

    deletePost(id) {
      const newPosts = this.posts.filter(post => {
        return post.id !== id;
      });
      this.posts = newPosts;
    },
  }
}
</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.app {
  padding: 20px;
}
</style>
