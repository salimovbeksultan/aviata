<template>
  <div id="options">
    <span v-for="key in keys" :key="key">
      <v-checkbox
        v-model="content"
        :value="key"
        :label="airlines[key]"
      ></v-checkbox>
    </span>
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
