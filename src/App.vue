<template>
  <v-app>
    <v-content>
      <AppHeader />
      <router-view></router-view>
      <AppFooter />
    </v-content>
  </v-app>
</template>

<script>
import AppHeader from './components/AppHeader.vue'
import AppFooter from './components/AppFooter.vue'

export default {
  name: 'App',
  components: {
    AppHeader,
    AppFooter
  },
  data: () => ({
    //
  }),
};
</script>
