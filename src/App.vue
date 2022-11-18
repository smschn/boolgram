<template>
  <div id="app">
    <MyNavbar />
    <MyMain />
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <!-- <HelloWorld msg="test"/> -->
  </div>
</template>

<script>
import MyNavbar from './components/MyNavbar.vue';
import MyMain from './components/Main/MyMain.vue';

export default {
  name: 'App',
  components: {
    MyNavbar,
    MyMain
  }
}
</script>

<style lang="scss">

  @import './styles/general.scss';
  @import './styles/variables.scss';

  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
  }

</style>