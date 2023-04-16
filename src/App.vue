<template>
  <div class="my-app">
    <h1>Twój e-mail to {{ email }}</h1>
    <input type="email" v-model="email">
    <div v-if="!email.includes('@')"> To nie jest email!</div>
    <div v-else-if="email.length < 10"> Adres jest za krótki, bo ma {{email.length}} znaki.</div>
    <div v-else-if="email.length < 15">Twój adres e-mail jest w sam raz.</div>
    <div v-else>Twój adres e-mail jest stanowczo za długi, bo ma {{email.length}} znaków.</div>
    <button @click="alertMyEmail()">Wyświetl mój e-mail w alercie</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      email: 'maromaniec@student.agh.edu.pl',
      password: ''
    };
  },
  methods: {
    alertMyEmail() {
      alert(this.email);
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


