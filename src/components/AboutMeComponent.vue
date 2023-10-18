<template>
  <div>
    <h1>About Me</h1>
    <div class="user-info">
      <div class="user-details">
         <h3>{{ user.name }}</h3>
         <h3>{{ user.surname }}</h3>
         <h3>{{ user.code }}</h3>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      buttonName: "LOGIN",
      user: {
        name: "Lydia",
        surname: "Kamynina",
        code: "IT2021",
      },
    };
  }
  
};
</script>

<style scoped>
</style>