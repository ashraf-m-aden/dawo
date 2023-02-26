<template>
  <div class="container-fluid" id="app">
    <v-app>
      <router-view />

      <!-- back to top start -->

      <v-btn
        @click="scrollToTop"
        :class="{ show: isVisible }"
        icon="mdi-arrow-up-thick"
        color="info"></v-btn>
      <!-- back to top end -->
    </v-app>
  </div>
</template>

<script setup lang="ts">
import { onMounted } from "vue";

let isVisible = false;

const scrollToTop = () => {
  window.scroll({
    top: 0,
    behavior: "smooth",
  });
};
onMounted(() => {
  window.addEventListener("scroll", () => {
    let scroll = window.scrollY;
    if (scroll >= 500) {
      isVisible = true;
    } else {
      isVisible = false;
    }
  });
});
</script>
<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
