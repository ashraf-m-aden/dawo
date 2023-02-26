<template>
  <!--====================  header area ====================-->
  <div class="row">
    <div class="col-12">
      <div class="first-header">
        <img
          class="logo"
          src="img/logo/dawo-low-resolution-color-logo.png"
          alt="" />
      </div>
    </div>
    <div class="col-12">
      <div class="second-header">
        <span class="item"
          ><router-link class="item-router" to="/about-us"
            >A propos</router-link
          >
        </span>
      </div>
    </div>
  </div>
  <!--====================  End of header area  ====================-->
</template>

<script setup lang="ts">
import { onMounted } from "vue";

let isSticky: boolean = false;
let items = [
  {
    label: "A propos de nous",
    icon: "pi pi-fw pi-file",
  },
];
// offcanvas mobile-menu
const mobiletoggleClass = (addRemoveClass: string, className: string) => {
  let el: Element = document.querySelector("#offcanvas-menu")!;
  if (addRemoveClass === "addClass") {
    el.classList.add(className);
  } else {
    el.classList.remove(className);
  }
};
onMounted(() => {
  window.addEventListener("scroll", () => {
    let scroll = window.scrollY;
    if (scroll >= 200) {
      isSticky = true;
    } else {
      isSticky = false;
    }
  });
});
</script>

<style lang="scss">
@import "../assets/scss/0-base/_variables.scss";
@import "../assets/scss/0-base/_mixins.scss";

.first-header {
  padding: 1rem;
  height: 100px;
  justify-content: center;
  position: relative;
  .logo {
    position: absolute;
    height: 50px;
    margin: auto;
    top: 0;
    bottom: 0;
    left: 5%;
    @include respond(tablet) {
      height: 10px;
      position: relative;
      height: 50px;
    }
  }
}
.second-header {
  background-color: $theme-color--default;
  height: 50px;
  display: flex;
  justify-content: center;
  width: 100%;
  .item {
    align-items: center;
    &:hover {
      border-bottom: 2px solid white;
    }
    &-router {
      color: $white;
      text-decoration: none;
    }
  }
}
</style>
