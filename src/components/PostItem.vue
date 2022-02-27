<template>
  <div class="post">
    <div class="post__text">
      <div>
        <strong>Название:</strong>
        {{ post.title }}
      </div>
      <div>
        <strong>Описание:</strong>
        {{ post.desc }}
      </div>
    </div>

    <div class="btns-container">
      <my-button class="btn" @click="deletePost(post)">Удалить</my-button>
    </div>
  </div>
</template>

<script>
import MyButton from "@/components/UI/MyButton.vue";

export default {
    props: {
        post: {
            type: Object,
            required: true,
        }
    },
    methods: {
      deletePost(post) {
        this.$emit('deletePost', post.id);
      }
    },
    components: { MyButton }
}
</script>

<style scoped lang="scss">
.post {
  padding: 15px;
  border: 2px solid teal;
  margin-top: 20px;
  border-radius: 4px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
</style>