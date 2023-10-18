<template>
  <header class="header" :style="{ backgroundColor: headerBackgroundColor}">
    <img src="@/assets/logo.png" alt="Logo" class="logo" />
    <h1>LABA.DABA</h1>
    <div class="user-info" v-if="isLoggedIn">
      <img src="@/assets/logo.png" alt="Avatar" class="avatar" />
     <div class="username">{{ fullName() }}</div>
    </div>
    <button @click="alert()">{{buttonName}}</button>
  </header>
</template>

<script>
export default {
  data() {
    return {
      buttonName: "LOGIN",
      isLoggedIn: false,
      headerBackgroundColor: "#473d4b",
      user: {
        name: "Lydia",
        surname: "Kamynina",
        code: "IT2021",
        full_name: "",
      },
    };
  },
  
  methods: {
    toggle() {
      this.$parent.toggle();
      if (this.buttonName === "LOGIN") {
        this.buttonName = "LOGOUT";
        this.isLoggedIn = true;
      } else {
        this.buttonName = "LOGIN";
        this.isLoggedIn = false;
      }
    },
    alert(){
      if (this.buttonName === "LOGIN") {
      if (window.confirm("Do you want to log in?")){
        this.toggle();
        this.headerBackgroundColor = "#4D4E50";
        this.$emit('user-logged-in', true);
      }
      }else {
        if (this.buttonName == "LOGOUT") {
          if (window.confirm("Do you want to log out?")){
            this.toggle();
            this.$parent.showHome = false;
            this.$parent.showAboutMe = false;
            this.headerBackgroundColor = "#473d4b";
            this.$emit('user-logged-out', true);
      }
        }
      }
    },
    fullName() {
    this.user.full_name = this.user.name + " " + this.user.surname;
    return this.user.full_name;
  },
  },
};
</script>



<style scoped>
header {
    font-style: robotiko;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1rem;
    width: 100%;
    color:#AC7685;
}

.logo {
  width: 40px;
  height: auto;
  margin-right: 10 px;
}

.button {
    background-color: #AC7685;
    color: #4D3E50;
    padding: 10px 20px;
    border: none;
    border-radius: 15px;
    font-weight: bold;
}
.avatar {
  width: 40px;
  height: 40px;
  border-radius: 50%;
  display: flex;
  justify-content: center;
  align-items: center;
  color: white;
  font-weight: bold;
  background-color: #4D3E50;
  margin-right: 10px; 
}

h1 {
    all: none;
    color: #AC7685;
}

username {
    color: white;
    font-style: robotiko;
}
</style>
