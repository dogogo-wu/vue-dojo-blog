<template>
  <div v-for="post in posts" :key="post.id">
    <SinglePost :post="post" />
  </div>
</template>

<script>
import { onMounted, onUnmounted, onUpdated } from '@vue/runtime-core';
import SinglePost from "./SinglePost.vue";

export default {
  props: ["posts"],
  components: { SinglePost },
  setup(props) {
    console.log(props.posts);

    onMounted(() => console.log("comp mounted"));
    onUnmounted(() => console.log("comp unmounted"));
    onUpdated(() => console.log("comp updated"));
  },
};
</script>

<style>
</style>