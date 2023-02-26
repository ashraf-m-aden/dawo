<template>
  <div>
    <div class="row">
      <div class="col-12">
        <v-card>
          <v-container>
            <v-progress-circular
              indeterminate
              color="primary"></v-progress-circular>
          </v-container>
        </v-card>
      </div>
      <div class="col-12">
        <v-card>
          <v-table fixed-header height="300px">
            <thead>
              <tr>
                <th class="text-left">Nom</th>
                <th class="text-left">Addresse</th>
                <th class="text-left">Prix</th>
                <th class="text-left">Numéro</th>
              </tr>
            </thead>
            <tbody>
              <tr v-for="(pharmacie, index) in pharmacies" :key="index">
                <td class="text-left">{{ pharmacie.name }}</td>
                <td class="text-left">{{ pharmacie.address }}</td>
                <td class="text-left">{{ pharmacie.number }}</td>
                <td class="text-left">{{ pharmacie.price }}</td>
              </tr>
            </tbody>
          </v-table>
        </v-card>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
const pharmacies = [
  {
    name: "Real-Time",
    price: "mdi-clock",
    address: "address",
    number: "number",
  },
];
</script>

<style lang="scss" scoped>
@keyframes rotate {
  from {
    -webkit-transform: rotate(0deg);
  }
  to {
    -webkit-transform: rotate(360deg);
  }
}
.loading {
  -webkit-animation-name: rotate;
  -webkit-animation-duration: 1s;
  -webkit-animation-iteration-count: infinite;
}
</style>
