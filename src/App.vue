<template>
  <v-app>
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
};
</script>
