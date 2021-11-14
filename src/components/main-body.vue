<template>
  <v-container id="body" class="pt-10">
    <v-row v-if="!demo">
      <v-col cols="12" md="4">
        <div class="filter">
          <main-options v-model="options"></main-options>
        </div>
      </v-col>
      <v-col cols="12" md="8">
        <div class="flights">
          <main-flights :options="options"></main-flights>
        </div>
      </v-col>
    </v-row>
    <v-row v-else>
      <v-col cols="12" md="4">
        <div class="menu"></div>
      </v-col>
      <v-col cols="12" md="8">
        <div class="content"></div>
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
    demo: false,
  }),
};
</script>
