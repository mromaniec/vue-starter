<template>
  <div class="my-app">
    <h1>Witaj w systemie do zapisów na zajęcia</h1>

    <div v-if = "loggedIn">
      Zalogowany na {{email}}
      <a @click="logMeOut()">Wyloguj</a>
    </div>
    <div v-else-if>
      <br>
      <label> Zaloguj się emailem: </label>
      <input type="email" v-model="email">
      <button @click="logMeIn()">Zaloguj się</button>
      <div v-if="!email.includes('@')"> To nie jest email!</div>
      <div v-else-if="email.length < 10"> Adres jest za krótki, bo ma {{email.length}} znaki.</div>
      <div v-else-if="email.length < 15">Twój adres e-mail jest w sam raz.</div>
      <div v-else>Twój adres e-mail jest stanowczo za długi, bo ma {{email.length}} znaków.</div>
    </div>
  </div>
</template>

<script>
import "milligram";

export default {
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
    logMeIn(){
      this.loggedIn = true;
    },
    logMeOut(){
      this.loggedIn = false;
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


