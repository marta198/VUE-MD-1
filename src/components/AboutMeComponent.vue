<template>
    <div class="aboutme">
      <h1>{{ msg }}</h1>
      <h3>{{ user.name }}</h3>
      <h3>{{ user.surname }}</h3>
      <h3>{{ user.code }}</h3>
    </div>
  </template>
  
  <script>
  export default {
    name: 'AboutMeComponent',
    data() {
        return {
            msg: "ABOUT ME",
            user: {
              name: "Marta",
              surname: "Balode",
              code: "IT21076"
            }
        }
    }
  }
  </script>
  
  <!-- Add "scoped" attribute to limit CSS to this component only -->
  <style>
  
  </style>
  