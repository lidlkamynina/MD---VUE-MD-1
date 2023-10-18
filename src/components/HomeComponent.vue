<template>
  <div>
    <h1>Home sweet Home</h1>
  </div>
</template>

<script>
export default {
  name: "HomeComponent",
  data() {
    return {
      isVisible: false,
    };
  },
  mounted() {
    this.isVisible = false;
  },
};
</script>

<style scoped>
</style>