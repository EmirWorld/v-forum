<template>
  <div class="thread rounded-bl-3xl flex bg-gray-200 flex-col">
    <div class="grid grid-cols-4 gap-4 ml-5 my-3">
      <div class="col-span-2">
        <p class="text-green-600">
          <router-link
            :to="{ name: 'ThreadShow', params: { id: thread['.key'] } }"
          >
            {{ thread.title }}
          </router-link>
        </p>
        <p>
          By
          <a class="text-green-600" href="#">{{ user.name }}</a>
          , {{ thread.publishedAt }}
        </p>
      </div>
      <div class="my-auto">
        <p class="text-right mr-5">{{ repliesCount }} replies</p>
      </div>
      <div class="flex">
        <img class="my-auto mr-5" src="#" alt="image" />
        <div class="flex flex-col">
          <p>name</p>
          <p>2 hours ago</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import SourceData from "@/data.json";

export default {
  name: "ThreadListItem",
  components: {},
  props: {
    thread: {
      required: true,
      type: Object,
    },
  },
  computed: {
    repliesCount() {
      return Object.keys(this.thread.posts).length - 1;
    },
    user() {
      return SourceData.users[this.thread.userId];
    },
  },
};
</script>
<style>
.thread:nth-child(2n + 0) {
  background-color: white;
  border-radius: 0;
}
</style>
