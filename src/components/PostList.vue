<template>
  <div class="mt-5 mb-5 flex flex-col items-center">
    <PostListItem v-for="post in posts" :key="post['.key']" :post="post" />
  </div>
</template>

<script>
import PostListItem from "@/components/PostListItem";
export default {
  name: "PostList",
  components: { PostListItem },
  props: {
    posts: {
      required: true,
      type: Array,
    },
  },
};
</script>

<style scoped></style>
