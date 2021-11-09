<template>
  <v-container id="body" class="pt-10">
    <v-row>
      <v-col cols="12" md="4">
        <main-options v-model="options"></main-options>
      </v-col>
      <v-col cols="12" md="8">
        <main-flights :options="options"></main-flights>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import MainFlights from "./main-flights.vue";
import MainOptions from "./main-options.vue";

export default {
  name: "MainBody",

  components: { MainOptions, MainFlights },

  methods: {},

  data: () => ({
    options: [],
  }),
};
</script>
