<template>
  <div id="app">
    <hello-left />
    <hello-right />
  </div>
</template>

<script>
import HelloLeft from "@/components/HelloLeft.vue";
import HelloRight from "@/components/HelloRight.vue";

export default {
  name: "App",
  components: {
    HelloLeft,
    HelloRight,
  },
};
</script>

<style></style>
