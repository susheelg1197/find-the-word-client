<template>
<div class="single-question quiz-answers">
  <div :class="answers.includes(index) ? 'checked-option': 'option'" v-for="(answer, index) in question.answers.slice(0,5)" class="quiz-answer" :key="answer.text">
    <button
      class="btn btn-action btn-answer"
      @click="toggleAnswer(index)"
      :class="getButtonClass(index)"
      :disabled="resolve"
    >
      <span class="question-num">{{indexToLetter(index)}}.</span>
      {{ answer.content }}
    </button>


    <!-- <blockquote class="quiz-explanation" v-if="resolve">
      <i class="icon icon-message"></i> {{ answer.explanation }}
    </blockquote> -->
  </div>
<div class="nav-question text-right" v-show="!resolve">
    <button class="btn btn-primary" @click="answer">{{ $t('answer') }}</button>
  </div>
</div>
</template>

<script>
export default {
  name: 'SingleQuestion',
  props: ['question', 'resolve', 'sendAnswer'],
  data(){
    return{
      answers:[],
    }
  },
  methods: {
    toggleAnswer(index) {
      if (this.answers.includes(index)) {
        this.answers = this.answers.filter(item => item !== index);
      } else {
        this.answers=[index];
      }
    },
    answer(){
      this.sendAnswer(JSON.parse(JSON.stringify(this.answers.sort())));
      this.answers=[]

    },
    getButtonClass(index) {
      const cl = [];

      if (this.resolve) {
        cl.push(this.question.resolution.includes(index) ? 'option-correct' : 'option-wrong');
      }

      if (this.question.answer && this.question.answer.includes(index)) {
        cl.push('checked-option');

        if (this.resolve) {
          cl.push(this.question.resolution.includes(index) ? 'checked-option-correct' : 'checked-option-wrong');
        }
      }

      return cl.join(' ');
    },
  },
};
</script>

<style scoped>
</style>
