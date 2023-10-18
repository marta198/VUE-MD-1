<template>
  <header>
    <HeaderComponent />
  </header>
  <body>
    <div class="row">
      <div v-show="showNavigation" class="column"> <NavigationComponent /> </div>
      <div class="column"> 
        <div v-show="showHome" v-if="showHome">
          <HomeComponent />
        </div>
        <div v-show="showAboutMe" v-if="showAboutMe">
          <AboutMeComponent />
        </div>   
      </div>
    </div>
    
  </body>
  
</template>

<script>
import HeaderComponent from './components/HeaderComponent.vue';
import NavigationComponent from './components/NavigationComponent.vue';
import HomeComponent from './components/HomeComponent.vue';
import AboutMeComponent from './components/AboutMeComponent.vue';

export default {
  name: 'App',
  components: {
    HeaderComponent,
    NavigationComponent,
    HomeComponent,
    AboutMeComponent
  },
  data() {
    return {
      showHome: false,
      showNavigation: false,
      showAboutMe: false,
      showFullName: false,
      showAvatar: false,
      isLoggedIn: false
    }
  },
  methods: {
    
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.row {
  display: flex;
}

.column {
  flex: 50%;
}

</style>
