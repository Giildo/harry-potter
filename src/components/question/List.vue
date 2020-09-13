<template>
  <section>
    <h1>{{ question.text }}</h1>

    <aside>
      <button v-for="(answer, index) in question.answers"
              :key="index"
              :class="{ answer__selected: index === answerIdSelected }"
              @click="onSelectAnswer(index)"
      >{{ index + 1 }}
      </button>
    </aside>

    <article>
      <img :src="imageSource" alt="Image associée à la réponse">
      {{ answerText }}
    </article>
  </section>
</template>

<script>
export default {
  name: 'List',

  props: {
    question: {
      required: true,
      type: Object,
    },
  },

  data: () => ({
    answerIdSelected: 0,
  }),

  computed: {
    answerSelected () {
      return this.question.answers[this.answerIdSelected]
    },
    answerText () {
      return this.answerSelected.text
    },
    imageSource () {
      return require(
          `../../assets/img/answers/q${this.question.id}/${this.answerSelected.pictureUrl}`,
      )
    },
  },

  methods: {
    onSelectAnswer (answerId) {
      this.answerIdSelected = answerId
      this.$emit('answer-selected', { questionId: this.question.id, answer: this.answerSelected})
    },
  },
}
</script>

<style lang="scss" scoped>
@import "src/assets/style/style";

section {
  display: grid;
  grid-template-areas: "title title" "list answer";
  grid-template-columns: 1fr 11fr;

  h1 {
    grid-area: title;
    font-size: 1.75rem;
    text-align: center;
    font-weight: 500;
  }

  aside {
    grid-area: list;
    display: flex;
    flex-direction: column;

    button {
      width: 50px;
      height: 50px;
      margin: 12px 0;
      border-radius: 3px;
      transition: background-color ease-in 100ms;

      &.answer__selected {
        background-color: $pageTitle;
      }

      &:hover {
        background-color: rgba(255, 255, 255, 0.1);
      }
    }
  }

  article {
    grid-area: answer;
    display: flex;
    flex-direction: column;
    align-items: center;
  }
}
</style>
