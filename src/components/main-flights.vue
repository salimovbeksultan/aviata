<template>
  <section>
    <div v-show="options.length == 0">
      <flight
        v-for="flight in flights"
        :key="flight.id"
        :flight="flight"
        :airlines="airlines"
        class="mb-5"
      ></flight>
    </div>
    <div v-show="options.length > 0">
      <flight
        v-for="flight in selectedFlights"
        :key="flight.id"
        :flight="flight"
        :airlines="airlines"
        class="mb-5"
      ></flight>
    </div>
  </section>
</template>

<script>
import json from "../data/results.json";
import flight from "./flight.vue";

export default {
  components: { flight },
  name: "MainFlights",
  props: {
    options: Array,
  },

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
    airlines: json.airlines,
    selectedFlights: [],
  }),
};
</script>

<style scoped></style>
