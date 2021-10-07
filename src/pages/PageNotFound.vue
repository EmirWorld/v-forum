<template>
  <div class="w-full h-screen flex justify-center items-center">
    <div class="text-center">
      <h1 class="text-6xl text-bold mb-5">Not Found</h1>
      <p>
        Ooops, we couldn't find what you are looking for.Why don't you
        <router-link class="text-green-600" :to="{ name: 'Home' }">
          <br />
          Go Home Instead
        </router-link>
      </p>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: "PageNotFound",
  components: {},
};
</script>
