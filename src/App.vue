<template>
  <v-app>
    <nav-bar/>
    <template-page>
      <template v-slot:title-page>
        Faîtes votre entrée à l'école des sorciers !
      </template>

      <router-view/>
    </template-page>
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
import TemplatePage from '@/components/template/TemplatePage'

export default {
  components: { TemplatePage, NavBar },
}
</script>
