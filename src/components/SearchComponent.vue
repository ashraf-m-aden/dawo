<template>
  <div class="row">
    <div class="col-12">
      <v-card>
        <v-container>
          <v-text>
            Vous cherchez un medicament précis? Ecrivez le dans la barre de
            recherche, et DAWO vous indiquera la pharmacie la plus proche qui le
            vend.
          </v-text>
          <v-parallax :src="paralax" class="paralax">
            <div
              class="d-flex flex-column fill-height justify-center align-center text-white">
              <div class="d-flex justify-content-between">
                <input type="text" class="form-control" />

                <v-btn icon="mdi-magnify" color="blue"></v-btn>
              </div>
            </div>
          </v-parallax>
        </v-container>
      </v-card>
    </div>
  </div>
</template>

<script setup lang="ts">
import paralax from "../../public/img/backgrounds/recherche.jpg";
import { ref } from "vue";

const data = ref();
const searchValue = ref();
const search = () => {
  if (searchValue.value != "") {
    //   $emit("medicament", searchValue.value);
    searchValue.value = "";
  }
};
</script>

<style lang="scss">
@import "../assets/scss/0-base/variables";
@import "../assets/scss/0-base/mixins";
.paralax {
  height: 200px;
  @include respond(tablet) {
    height: 200px;
  }
}
</style>
