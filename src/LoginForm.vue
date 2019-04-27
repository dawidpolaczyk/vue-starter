<template>
   <div>
      <label>Zaloguj się e-mailem</label>

    <div v-if="logged">
        Witaj {{ email }}<br><br>
      <button @click="logOut()">Wyloguj</button>
    </div>

    <div v-else>
      <button @click="logIn()" button-label="test"></button>
    </div>
  </div>
</template>

<script>
export default {
 data() {
     return {
        email: '',
        password: '',
        logged: false
     }
 },
 methods: {
     logIn(username) {
        this.logged = true;
        this.authenticatedUsername = username;
        this.$emit('login', this.email);
     },
        logOut() {
        this.logged = false;
        this.email ='';
    }
 }
}
</script>