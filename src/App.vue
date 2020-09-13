<template>
  <v-app>
    <nav-bar/>
    <router-view/>
  </v-app>
</template>

<style lang="scss">
html {
  font-size: 20px;

  #app {
    font-family: Roboto, sans-serif;
  }
}
</style>
<script>
import NavBar from '@/components/template/NavBar'
export default {
  components: { NavBar },
}
</script>
