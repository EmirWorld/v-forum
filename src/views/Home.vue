<template>
  <div class="home bg-gray-100">
    <img alt="Vue logo" src="../assets/logo.png" />
    <PageHome />
  </div>
</template>

<script>
// @ is an alias to /src
import PageHome from "@/pages/PageHome.vue";

export default {
  name: "Home",
  components: {
    PageHome,
  },
};
</script>
