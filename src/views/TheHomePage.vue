<template>
  <div>
    <TheHeader></TheHeader>
    <TheHero></TheHero>
    <SearchComponent @medicament="fetchData" />
    <v-divider></v-divider>

    <TheMedecins></TheMedecins>
    <!-- <RechercheResult :medicament="medicament" :loading="loading" /> -->

    <!-- <Footer /> -->
    <!-- <OffCanvasMobileMenu /> -->
  </div>
</template>

<script setup lang="ts">
import * as data from "../data/slider.json";
import { ref } from "vue";
import TheHeader from "@/components/TheHeader.vue";
import TheHero from "@/components/TheHero.vue";
import SearchComponent from "@/components/SearchComponent.vue";
import TheMedecins from "@/components/TheMedecins.vue";

const medicament = ref();
let loading = false;

const fetchData = (data: any) => {
  loading = true;
  setTimeout(() => {
    medicament.value = data;
    loading = false;
  }, 2000);
};
</script>
