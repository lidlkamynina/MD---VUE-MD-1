<template>
  <nav class="navigation">
    <ul>
      <li @click="showHome" :class="{ active: isHomeActive }" class="nav-button">Home</li>
      <li @click="showAboutMe" :class="{ active: isAboutMeActive }" class="nav-button">About Me</li>
    </ul>
  </nav>
</template>

<script>
export default {
  data() {
    return {
      isHomeActive: true,
      isAboutMeActive: false,
    };
  },
  methods: {
    showHome() {
       this.$parent.toggle1();
      this.$emit("show-home");
      this.isHomeActive = true;
      this.isAboutMeActive = false;
    },
    showAboutMe() {
      this.$parent.toggle1();
      this.$emit("show-aboutme");
      this.isHomeActive = false;
      this.isAboutMeActive = true;
    },
  },
};
</script>

<style scoped>
.navigation {
  background-color: #C8BAB3;
  color: white;
}

.nav-button {
  cursor: pointer;
  padding: 10px 20px;
  background-color: #AC7685;
  color: white;
  border: none;
  border-radius: 5px;
  margin: 5px;
  font-weight: bold;
  display: block;
  text-align: center;
}

.nav-button.active {
  background-color: #4D3E50;
}

.nav-button:hover {
  background-color: #0a2338;
}
</style>