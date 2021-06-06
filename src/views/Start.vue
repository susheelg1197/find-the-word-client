<template>
  <div>
    <div
      class="quiz-start quiz-intro"
      v-for="(quiz, index) in quizes"
      :key="index"
    >
      <h1>{{quiz.name}}</h1>

      <div class="quiz-description col-7 col-sm-auto">
        {{ quiz.description }}
      </div>

      <div class="quiz-nav">
        <button class="btn btn-primary btn-quiz-start" @click="$emit('start',quiz.name)">
          {{ $t("start_quiz") }}
        </button>
      </div>
      <hr />
    </div>
  </div>
</template>

<script>
export default {
  name: 'Start',
  props: ['quiz'],
  data() {
    return {
      quizes: [{
        name: 'Gre Rapid fire',
        description: 'Gre rapid fire',

      },
      {
        name: 'Gre Rapid fire2',
        description: 'Gre rapid fire',

      },
      {
        name: 'Gre Rapid fire3',
        description: 'Gre rapid fire',

      }],
    };
  },
};
</script>

<style scoped>
.quiz-start {
  padding: 20px;
}

.btn-quiz-start {
  margin-top: 20px;
  padding: 6px 25px 15px;
  height: 2rem;
}

.quiz-start h1:after {
  display: block;
  content: "";
  position: relative;
  left: 0;
  bottom: 0;
  max-width: 40px;
  height: 1px;
  border-bottom: 3px solid #5755d9;
  margin: 0;
  padding: 8px 0;
}
</style>
