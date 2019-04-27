<template>
  <div id="app">

    <h1>Witaj w systemie do zapisów na zajęcia</h1><br><br>
    
    <div v-if="logged==false">
      Zaloguj się emailem
      <input type="email" v-model="email">
      <button @click="logIn()">Wchodzę</button>
    </div>

    <div v-else="logged==true">
      Witaj {{ email }}
      <button @click="logOut()">Wyloguj</button>
    </div>

  </div>
</template>

<script>
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
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
