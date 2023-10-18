<template>
    <div class="navigation">
        <button type="button" @click="showHome()" :class="{active: isHomeActive}" class = 'btn'>HOME</button>
        <button type="button" @click="showAboutMe()" :class="{active: isAboutMeActive}" class = 'btn'>ABOUT ME</button>
    </div>
  </template>
  
  <script>
  export default {
    name: 'NavigationComponent',
    data() {
        return {
            isHomeActive: true,
            isAboutMeActive: false
        }
    },
    methods: {
      showHome() {
        this.$parent.showHome = true;
        this.$parent.showAboutMe = false;
        this.isHomeActive = true;
        this.isAboutMeActive = false;
      },
      showAboutMe() {
        this.$parent.showAboutMe = true;
        this.$parent.showHome = false;
        this.isHomeActive = false;
        this.isAboutMeActive = true;
      }
    }
  }
  </script>
  
  <!-- Add "scoped" attribute to limit CSS to this component only -->
  <style scoped>
    .navigation {
      margin-top: 1rem;
      display: flex;
      flex-direction: column;
      align-items: flex-start;
    }
    .btn {
      border: none;
      outline: none;
      padding: 10px 16px;
      background-color: #f1f1f1;
      cursor: pointer;
      font-size: 18px;
    }
    .active {
      background-color: #666;
      color: white;
    }
  </style>
