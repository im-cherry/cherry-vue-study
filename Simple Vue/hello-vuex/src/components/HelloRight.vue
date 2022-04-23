<template>
  <div>value : {{ counter }}</div>
</template>

<script>
import { mapGetters } from "vuex";

export default {
  name: "HelloRight",
  computed: {
    ...mapGetters(["counter"]),
  },
};
</script>

<style></style>
