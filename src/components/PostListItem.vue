<template>
  <div class="mb-2 w-full shadow-md flex">
    <div class="px-6 py-6 w-2/12">
      <div class="flex items-center flex-1 flex-col">
        <p class="mb-2 text-lg text-green-700">
          {{ user.name }}
        </p>
        <a href="#" class="rouded-full overflow-hidden">
          <img :src="user.avatar" alt="user image" />
        </a>
        <p class="mt-4">{{ userPostCount }} posts</p>
      </div>
    </div>
    <div class="w-full px-6 py-6">
      <p class="font-sm">{{ post.text }}</p>
    </div>
  </div>
</template>

<script>
import SourceData from "@/data.json";
export default {
  name: "PostListItem",
  props: {
    post: {
      required: true,
      type: Object,
    },
  },
  computed: {
    user() {
      return SourceData.users[this.post.userId];
    },
    userPostCount() {
      return Object.keys(this.user.posts).length;
    },
  },
};
</script>

<style scoped></style>
