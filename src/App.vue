<template>
  <div id="app">
    <h1>Witaj w systemie do zapisów na zajęcia</h1><br><br>
    
    <div v-if="logged">
        Witaj {{ email }}<br><br>
      <button @click="logOut()">Wyloguj</button>
    </div>

    <div v-else>
      <login-form2 @login="logIn($event)" button-label="test"></login-form2>
    </div>
</div>

</template>

<script>
import "milligram";
import LoginForm2 from "./LoginForm2";
export default {
    components: {
      LoginForm2
    },
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

<style>
</style>
