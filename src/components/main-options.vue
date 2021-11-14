<template>
  <v-expansion-panels>
    <v-expansion-panel expand>
      <v-expansion-panel-header>
        <strong>Авиакомпании</strong>
      </v-expansion-panel-header>
      <v-expansion-panel-content>
        <v-checkbox
          v-for="key in keys"
          :key="key"
          v-model="content"
          :value="key"
          :label="airlines[key]"
          hide-details
        ></v-checkbox>
      </v-expansion-panel-content>
    </v-expansion-panel>
  </v-expansion-panels>
</template>

<script>
import json from "../data/results.json";

export default {
  name: "MainOptions",
  props: ["value"],

  watch: {
    content: function () {
      this.$emit("input", this.content);
    },
  },

  data: () => ({
    keys: Object.keys(json.airlines),
    airlines: json.airlines,
    content: [],
    panel: [0],
  }),
};
</script>
