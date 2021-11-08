<template>
  <div id="main-flights">
    <div v-if="selectedFlights.length > 0" id="selected-flights">
      <ul class="flight" v-for="flight in selectedFlights" :key="flight.id">
        <li>
          <flight :flight="flight"></flight>
        </li>
      </ul>
    </div>
    <div v-else id="flights">
      <ul class="flight" v-for="flight in flights" :key="flight.id">
        <li>
          <flight :flight="flight"></flight>
        </li>
      </ul>
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
        this.selectedFlights = this.flights.filter((flight) => {
          if (this.options.includes(flight.validating_carrier)) return flight;
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
