<template>
  <div id="options">
    <v-row>
      <v-col class="pb-0 mx-2">
        <strong>Авиакомпании</strong>
      </v-col>
    </v-row>
    <v-row>
      <v-col class="pt-0 mx-2">
        <div v-for="key in keys" :key="key">
          <v-checkbox
            v-model="content"
            :value="key"
            :label="airlines[key]"
            hide-details
          ></v-checkbox>
        </div>
      </v-col>
    </v-row>
  </div>
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
  }),
};
</script>

<style>
.options {
  background: #f5f5f5;
  border-radius: 4px;
}
</style>
