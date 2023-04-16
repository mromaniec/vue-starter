<template>
  <div v-if = "email">
    Zalogowany na {{email}}
    <a @click="logMeOut()">Wyloguj</a>
</template>

<script>
export default {
  name: "UserState"
}
</script>

<style scoped>

</style>