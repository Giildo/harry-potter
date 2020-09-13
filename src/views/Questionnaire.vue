<template>
  <section>
    <Component v-for="question in questions"
               :is="question.answerType"
               :key="question.id"
               :question="question"
               @answer-selected="onAnswerSelected"
    />
  </section>
</template>

<script>
import List from '@/components/question/List'
import config from '@/assets/config/questions.json'

export default {
  name: 'Questionnaire',

  components: { List },

  data: () => ({
    questions: [],
    answersSelected: [],
  }),

  created () {
    this.questions = config
  },

  methods: {
    onAnswerSelected ({ questionId, answer }) {
      const answerSelected = this.answersSelected.find(answerSaved => answerSaved.questionId === questionId)
      answerSelected === undefined
      ? this.answersSelected.push({ questionId, answer })
      : answerSelected.answer = answer
    },
  },
}
</script>

<style scoped>

</style>
