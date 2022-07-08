<template>
  <div class="home">
    <h1>Home</h1>
    <PostList :posts="posts" v-if="showPost"/>
    <button @click="showPost = !showPost">Toggle posts</button>
    <button @click="posts.pop()">Remove a post</button>
  </div>
</template>

<script>
import { ref } from "vue";
import PostList from "../components/PostList.vue";

export default {
  name: "Home",
  components: { PostList },
  setup() {
    const posts = ref([
      {
        id: 1,
        title: "Welcom to the blog",
        content:
          "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.",
      },
      {
        id: 2,
        title: "Top 5 css tips",
        content:
          "It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters, as opposed to using 'Content here, content here', making it look like readable English. Many desktop publishing packages and web page editors now use Lorem Ipsum as their default model text, and a search for 'lorem ipsum' will uncover many web sites still in their infancy. Various versions have evolved over the years, sometimes by accident, sometimes on purpose (injected humour and the like).",
      },
      { id: 3, title: "My profolio", content: "lorem" },
    ]);
    const showPost = ref(true);

    return { posts, showPost };
  },
};
</script>
