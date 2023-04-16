<template>
  <div>
    <label>Zaloguj się e-mailem</label>
    <input type="email" v-model="email">
    <button @click="enter()">{{buttonLabel}}</button>

    <div v-if="!email.includes('@')"> To nie jest email!</div>
    <div v-else-if="email.length < 10"> Adres jest za krótki, bo ma {{email.length}} znaki.</div>
    <div v-else-if="email.length < 15">Twój adres e-mail jest w sam raz.</div>
    <div v-else>Twój adres e-mail jest stanowczo za długi, bo ma {{email.length}} znaków.</div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      email: ''
    }
  },
  methods: {
    enter() {
      this.$emit('login', this.email);
    }
  },
  props: {buttonLabel: String}
}

</script>

<style scoped>

</style>