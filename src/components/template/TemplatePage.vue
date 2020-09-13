<template>
  <section id="template__section">
    <div class="container">
      <v-alert class="title__page" elevation="12">
        <slot name="title-page"/>
      </v-alert>

      <article>
        <slot/>
      </article>
    </div>
  </section>
</template>

<script>
export default {
  name: 'TemplatePage',

  data: () => ({
    title: '',
  }),
}
</script>

<style lang="scss" scoped>
@import "src/assets/style/style";

#template__section {
  background-color: $pageBackground;
  padding-top: 10px;
  min-height: calc(100vh - 128px);

  .container {
    @include container;

    .title__page {
      background-color: $pageTitle;
      margin: 0 20px;
      text-align: center;
      color: white;
      font-weight: 700;
      font-size: 1rem;
      z-index: 10;
    }

    article {
      padding: 40px 20px 20px;
      border-radius: 5px;
      background-color: $textContainerBackground;
      color: white;
      position: relative;
      top: -20px;
      z-index: 1;
    }
  }
}
</style>
