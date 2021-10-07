<template>
  <div id="nav" class="container-fluid h-8 flex items-center bg-gray-500">
    <div class="mx-auto text-white container flex">
      <div class="ml-auto">
        <router-link class="mr-2 hover:text-gray-200" to="/">Home</router-link>
        |
        <router-link class="ml-2 hover:text-gray-200" to="/about">
          About
        </router-link>
      </div>
    </div>
  </div>
  <router-view />
</template>
