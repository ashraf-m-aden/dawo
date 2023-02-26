<template>
  <div>
    <div class="row">
      <div class="col-12">
        <div class="hero">
          <div class="hero-text">
            <h1>Trouvez la pharmacie la plus proche</h1>
            <p>DAWO regroupe les données de nombreuses pharmacie</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts"></script>

<style lang="scss" scoped>
@import "../assets/scss/0-base/variables";
@import "../assets/scss/0-base/mixins";

.hero {
  height: 500px;
  background-image: url("../../public/img/slider/hero.jpg");
  align-items: center;
  display: flex;
  @include respond(tablet) {
    height: 400px;
    background-size: cover;
  }

  &-text {
    color: white;
    width: 50%;
    display: flex;
    flex-direction: column;
    text-align: left;
    padding-left: 1rem;
    h1 {
      font-size: 60px;
      text-justify: left;

      @include respond(tablet) {
        font-weight: 800;
        font-size: 40px;
      }
    }
  }
}
</style>
