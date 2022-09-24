<template>
  <SideNavigationBar msg="Welcome to Your Vue.js App"/>
  <GuestBook/>
</template>

<script>
import SideNavigationBar from './components/SideNavigationBar.vue';
import GuestBook from './components/GuestBook.vue';

export default {
  name: 'App',
  components: {
    SideNavigationBar,
    GuestBook
}
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #000000;
  background-color: #d6d6d6;
  width: 100vw;
  height: 100vh;
}
</style>
