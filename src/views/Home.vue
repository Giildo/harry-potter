<template>
  <section>
    <p>Et si vous aviez été à Poudlard... Dans quelle maison auriez-vous été ?</p>

    <p>Grâce à ce quiz qui reprend TOUTES les questions officielles de J.K. Rowling, vous pourrez non seulement répondre
      à cette question de manière très précise, mais vous connaîtrez aussi le pourcentage exact de votre caractère selon
      les différentes maisons !</p>

    <p>Êtes-vous prêt à franchir le pas...?</p>

    <img :src="require('../assets/img/hogwarts.jpg')"
         alt="Image représentant le blason de Poudlard avec les symboles des 4 maisons"
    />

    <v-btn x-large color="#2bbbad">Commencer</v-btn>

    <p>~ Ce quiz a été fait par un fan et n'est donc nullement affilié à WIZARDING WORLD ou à UNIVERSAL STUDIO, merci de
      votre compréhension !</p>
  </section>
</template>

<script>
export default {
  name: 'Home',
}
</script>

<style lang="scss" scoped>
@import "src/assets/style/style";

section {
  display: flex;
  flex-direction: column;
  align-items: center;

  p {
    text-align: center;
    font-size: 1.25rem;
    font-weight: 500;

    &:first-child {
      font-size: 1.5rem;
    }

    &:last-child {
      font-size: 0.825rem;
    }
  }

  img {
    width: 100%;
  }

  @media all and (min-width: $m) {
    img {
      width: 66%;
    }
  }

  @media all and (min-width: $l) {
    img {
      width: 50%;
    }
  }

  button {
    margin: 7.5px;
  }
}
</style>
