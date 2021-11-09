<template>
  <div id="main-flights">
    <div v-if="this.options.length > 0" id="selected-flights">
      <v-row v-for="flight in selectedFlights" :key="flight.id">
        <v-col cols="12">
          <flight :flight="flight"></flight>
        </v-col>
      </v-row>
    </div>
    <div v-else id="flights">
      <v-row v-for="flight in flights" :key="flight.id">
        <v-col cols="12">
          <flight :flight="flight"></flight>
        </v-col>
      </v-row>
    </div>
  </div>
</template>

<script>
import json from "../data/results.json";
import flight from "./flight.vue";

export default {
  components: { flight },
  name: "MainFlights",
  props: ["options"],

  watch: {
    options: function () {
      if (this.options.length > 0) {
        this.selectedFlights = this.flights.filter((e) => {
          if (this.options.includes(e.validating_carrier)) return e;
        });
      }
    },
  },

  data: () => ({
    flights: json.flights,
    selectedFlights: [],
  }),
};
</script>

<style scoped></style>
