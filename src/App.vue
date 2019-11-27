/*eslint no-console: ["error", { allow: ["warn", "log"] }] */

<template>
  <div id="app">
    <AppHeader />
    <h1>Next PATCO</h1>

    <!-- route outlet -->
    <!-- component matched by the route will render here -->
    <router-view></router-view>

    <AppFooter />
  </div>
</template>

<script>
import AppHeader from './components/AppHeader.vue'
import AppFooter from './components/AppFooter.vue'

export default {
  name: 'app',
  components: {
    AppHeader,
    AppFooter
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
