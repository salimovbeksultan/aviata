<template>
  <v-app :style="{ background: $vuetify.theme.themes[theme].background }">
    <v-main>
      <main-body></main-body>
    </v-main>
  </v-app>
</template>

<script>
import MainBody from "./components/main-body.vue";
export default {
  name: "App",

  components: { MainBody },

  computed: {
    theme() {
      return this.$vuetify.theme.dark ? "dark" : "light";
    },
  },
};
</script>
