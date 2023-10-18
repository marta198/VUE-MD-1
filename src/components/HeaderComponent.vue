<template>
    <div class="header"  :class="{ 'alt-background': isAlternativeBackground }">
      <div class = "left">
        <img src="../assets/logo.svg" />
        <h1>{{ title }}</h1>
      </div>
      <div class = "right">
        <div v-show="this.$parent.showAvatar" class="circle"></div>
        <div> </div>
        <h v-show="this.$parent.showFullName">{{ newName() }}</h>
        <div> </div>
        <button class = "btn" @click="toggleButton">{{ buttonName }}</button>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'HeaderComponent',
    data() {
        return {
            title: "Vue Project",
            user: {
                name: "Marta",
                surname: "Balode",
                code: "IT21076",
                full_name: ""
            },
            buttonName: "Login",
            isAlternativeBackground: false
        }
    },
    methods: {
      newName() {
        return this.user.full_name = this.user.name + " " + this.user.surname;
      },
      toggleButton() {
        if (this.$parent.isLoggedIn) {
          if (confirm("Do you want to log out?") == true) {
            this.buttonName = "Login";
            this.$parent.showHome = false;
            this.$parent.showNavigation = false;
            this.$parent.showAboutMe = false;
            this.$parent.showAvatar = false;
            this.$parent.showFullName = false;
            this.$parent.isLoggedIn = !this.$parent.isLoggedIn;
            this.isAlternativeBackground = false;
          }
        } else {
          if (confirm("Do you want to log in") == true) {
            this.buttonName = "Logout";
            this.$parent.showHome = true;
            this.$parent.showNavigation = true;
            this.$parent.showAboutMe = true;
            this.$parent.showAvatar = true;
            this.$parent.showFullName = true;
            this.$parent.isLoggedIn = !this.$parent.isLoggedIn;
            this.isAlternativeBackground = true;
          }
        }
        this.$emit('user-logged-in');
      }
    }
}
  </script>
  
  <!-- Add "scoped" attribute to limit CSS to this component only -->
  <style scoped>
  .header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    color: #fff;
  }

  .left {
    display: flex;
    align-items: center;
  }

  .right {
    display: flex;
    align-items: center;
    gap: 1rem;
  }

  .btn {
      border: none;
      outline: none;
      padding: 10px 16px;
      background-color: #f1f1f1;
      cursor: pointer;
      font-size: 15px;
      margin-right: 1rem;
    }

  .circle {
      background-color: #28c495;
      height: 50px;
      width: 50px;
      border-radius: 50%;
    }

    .header {
      background-color: #333;
    }

    .alt-background {
      background-color: #8096ab;
    }

  </style>
  
