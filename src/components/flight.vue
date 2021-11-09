<template>
  <div class="flight">
    <v-row class="mb-5">
      <v-col cols="8"></v-col>
      <v-col cols="4" class="flight-menu">
        <div class="d-flex flex-column">
          <span class="text-h6 mx-auto" v-text="flight.price"></span>
          <v-btn block> Выбрать </v-btn>
        </div>
      </v-col>
    </v-row>
  </div>
</template>

<script>
export default {
  name: "Flight",
  props: ["flight"],
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
