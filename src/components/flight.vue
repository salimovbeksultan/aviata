<template>
  <div class="flight">
    <v-row class="mb-5">
      <v-col cols="8">
        <div></div>
      </v-col>
      <v-col cols="4" class="flight-menu">
        <div class="d-flex flex-column">
          <div class="mx-auto">
            <span class="text-h5 mx-auto" v-text="flight.price"></span>
            <span class="text-h6"> {{ formatCurrency() }}</span>
          </div>
          <v-btn color="primary" block> Выбрать </v-btn>
        </div>
      </v-col>
    </v-row>
  </div>
</template>

<script>
export default {
  name: "Flight",
  props: ["flight"],
  methods: {
    formatCurrency() {
      switch (this.flight.currency) {
        case "KZT":
          return "₸";
        case "RUB":
          return "₽";
        default:
          return "";
      }
    },
  },
};
</script>

<style>
.flight {
  background: #ffffff;
  box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.15);
  border-radius: 4px;
}

.flight-menu {
  background: #f5f5f5;
  border-radius: 0px 4px 4px 0px;
}
</style>
