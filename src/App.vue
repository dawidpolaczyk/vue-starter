<template>
  <div id="app">

    <h1>Witaj w systemie do zapisów na zajęcia</h1><br><br>
    
    <div v-if="logged==false">
      Zaloguj się emailem<br>
      <input type="email" v-model="email">
      <button @click="logIn()">Wchodzę</button>
    </div>

    <div v-else="logged==true">
      Witaj {{ email }}<br><br>
      <button @click="logOut()">Wyloguj</button>
    </div>

  </div>
</template>

<script>
import "milligram";
export default {
    data() {
      return {
        email: '',
        password: 'testtest',
        logged: false
      };
    },
    methods: {
     logIn() {
        this.logged = true;
      },
      logOut() {
        this.logged = false;
      }
    }
  }

</script>

<style>
</style>
