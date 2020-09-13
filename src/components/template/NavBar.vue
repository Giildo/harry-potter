<template>
  <header>
    <router-link :to="{ name: 'Home' }">
      <img :src="require('../../assets/img/logo.png')" alt="Logo du site représentant le Choixpeau de Harry potter."/>
      Quiz du Choixpeau
    </router-link>
  </header>
</template>

<script>
export default {
  name: 'NavBar',
}
</script>

<style lang="scss" scoped>
@import "src/assets/style/style";

header {
  a {
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: $navbar;
    font-weight: bold;
    font-size: 3rem;
    color: white;
    text-decoration: none;
  }
}
</style>
