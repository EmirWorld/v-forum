<template>
  <div class="container mx-auto">
    <div class="flex h-10 items-center space-x-2 text-gray-500">
      <svg
        xmlns="http://www.w3.org/2000/svg"
        class="h-5 w-5"
        fill="none"
        viewBox="0 0 24 24"
        stroke="currentColor"
      >
        <path
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="2"
          d="M3 12l2-2m0 0l7-7 7 7M5 10v10a1 1 0 001 1h3m10-11l2 2m-2-2v10a1 1 0 01-1 1h-3m-6 0a1 1 0 001-1v-4a1 1 0 011-1h2a1 1 0 011 1v4a1 1 0 001 1m-6 0h6"
        />
      </svg>
      <a href="#" class="hover:text-gray-600">Home</a>
      <p>></p>
      <a href="#" class="hover:text-gray-600">Home</a>
      <p>></p>
      <a href="#" class="hover:text-gray-600">Home</a>
    </div>

    <h1 class="text-xl mt-5 text-start font-bold">{{ thread.title }}</h1>
    <PostList :posts="posts" />
  </div>
</template>

<script>
import sourceData from "@/data.json";
import PostList from "@/components/PostList";
export default {
  name: "PageThreadShow",
  components: { PostList },
  props: {
    id: {
      required: true,
      type: String,
    },
  },

  data() {
    return {
      thread: sourceData.threads[this.id],
    };
  },

  computed: {
    posts() {
      const postIds = Object.values(this.thread.posts);
      return Object.values(sourceData.posts).filter((post) =>
        postIds.includes(post[".key"])
      );
    },
  },

  created() {
    console.log(this.id);
    console.log(this.thread);
  },
};
</script>
