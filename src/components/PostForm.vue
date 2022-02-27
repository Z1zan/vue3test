<template>
  <form class="form" @submit.prevent>
    <h4 class="title">Создание поста</h4>
    <input
      v-model="post.title"
      class="input"
      type="text" 
      placeholder="Название"
    />

    <input
      v-model="post.desc"
      class="input"
      type="text"
      placeholder="Описание"
    />
    <my-button class="btn" @click="createPost()">Создать</my-button>
  </form>
</template>

<script>
import MyButton from "@/components/UI/MyButton.vue";
export default {
    data() {
        return {
            post: {
                title: "",
                desc: "",
            }
        };
    },
    methods: {
        createPost() {
            this.post.id = Date.now();
            this.$emit("createPost", this.post);
            this.post = {
                title: "",
                desc: "",
            };
        },
    },
    components: { MyButton }
}
</script>

<style scoped lang="scss">
.form {
  display: flex;
  flex-direction: column;
  align-items: center;


  .title {
    margin-bottom: 15px;
  }
  .input {
    width: 100%;
    border: 1px solid teal;
    padding: 10px 15px;
    margin-bottom: 10px;
    border-radius: 4px;
  }
}
</style>