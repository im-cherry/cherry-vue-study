<template>
  <div>
    <button @click="subCounter">-</button>
    <button @click="addCounter">+</button>
  </div>
</template>

<script>
import { mapActions } from "vuex";
export default {
  name: "HelloLeft",
  methods: {
    ...mapActions(["addCounter", "subCounter"]),
  },
};
</script>

<style></style>
