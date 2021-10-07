<template>
  <div class="mx-5">
    <div class="bg-white">
      <div class="bg-gray-900 rounded-bl-3xl mt-24 pt-5 pb-5 z-10 relative">
        <p class="text-gray-300 text-4xl ml-5">Threads</p>
      </div>
    </div>
    <ThreadListItem
      v-for="thread in threads"
      :key="thread['.key']"
      :thread="thread"
    />
  </div>
</template>

<script>
import ThreadListItem from "@/components/ThreadListItem";
export default {
  name: "ThreadList",
  components: { ThreadListItem },
  props: {
    threads: {
      required: true,
      type: Array,
    },
  },
};
</script>
