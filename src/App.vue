<template>
  <div class="my-app">
    <h1>Witaj w systemie do zapisów na zajęcia</h1>

    <div v-if = "email">
      Zalogowany na {{email}}
      <a @click="logMeOut()">Wyloguj</a>
    </div>
    <div v-else>
      <LoginForm @login="(username) => logMeIn(username)" :button-label="Math.random() < 0.5 ? 'Zaloguj mnie' : 'Etykieta B'"></LoginForm>
    </div>
  </div>
</template>

<script>
import "milligram";
import LoginForm from "./LoginForm";
import UserState from "./UserState";

export default {
  components: {LoginForm},
  data() {
    return {
      email: '',
      loggedIn: false,
      password: ''
    };
  },
  methods: {
    alertMyEmail() {
      alert(this.email);
    },
    logMeIn(username){
      this.email = username;
      //this.loggedIn = true;
    },
    logMeOut(){
      this.email = '';
      //this.loggedIn = false;
    }
  }
}
</script>

<style>
.my-app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
}
</style>


