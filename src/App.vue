<template>
<Header>
  <HeaderComponent></HeaderComponent>
  
</Header>
<main>
  <div class="container">
        <div class="row">
          <div class="column navigation-column" v-show="showNav">
            <NavigationComponent @show-home="showHomeComponent" @show-aboutme="showAboutMeComponent" />
          </div>
        <div class="column content-column">
            <HomeComponent v-show="showHome" v-if="showHome" />
            <AboutMeComponent v-show="showAboutMe" v-if="showAboutMe" />
          </div>
        </div>
    </div>
</main>
   
</template>

<script>
import HeaderComponent from "./components/HeaderComponent.vue";
import NavigationComponent from "./components/NavigationComponent.vue";
import AboutMeComponent from "./components/AboutMeComponent.vue";  
import HomeComponent from './components/HomeComponent.vue';

export default {
  name: "App",
  components: {
    HeaderComponent,
    NavigationComponent,
    AboutMeComponent,
    HomeComponent,
    
  },
  data() {
    return {
      showHome: false,
      showNav: false,
      showHomeComponent: false,
      showAboutMeComponent: false,
      showAboutMe: false,
      buttonClicked: "HOME",
    }
  },
  methods: {
    toggle1(){
      this.showAboutMe = !this.showAboutMe;
      this.showHome = !this.showHome;
    },
    toggle() {
      this.showHome = !this.showHome;
      this.showNav = !this.showNav;
      if (this.buttonName === "LOGIN") {
        this.buttonName = "LOGOUT";
      } else {
        this.buttonName = "LOGIN";
      }
      
    },
    
  }
};
</script>

<style scoped>
.row {
  display: flex;
  flex-direction: row;
  flex: 1;
  height: 100vh;
  width: 100%;
  color: white;
  background-color: #C8BAB3;
}

.col {
  display: flex;
  flex-direction: column;
  flex: 1;
  height: 100vh;
  width: 50%;
  color: green;
  background-color: #C8BAB3;
}

.nav-column {
  background-color: black;
  color: white;
}
body {
   display: flex;
  background-color: #4D3E50;
}
</style>