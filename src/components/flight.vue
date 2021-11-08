<template>
  <div>
    {{ flight.id }}
  </div>
</template>

<script>
export default {
  name: "Flight",
  props: ["flight"],
};
</script>
