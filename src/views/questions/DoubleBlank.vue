<template>
<div class="multiple-question quiz-answers container-fluid">
   <div class="quiz-answer col-md-6">
  <div v-for="(answer, index) in question.answers" :key="index">
  <div
  v-if="index<3"
    class="quiz-answer row mr-2 mb-2"
    :key="answer.text"
    :class="answers.includes(index) ? 'checked-option': 'option'"
    :disabled="resolve"
  >
    <button
      class="btn btn-action btn-answer"
      :disabled="resolve"
      @click="toggleAnswer(index)"
      :class="getButtonClass(index)"
    >
      <span class="question-num">{{indexToLetter(index)}}.</span>
      {{ answer.content }}
    </button>

    <!-- <blockquote class="quiz-explanation" v-if="resolve">
      <i class="icon icon-message"></i> {{ answer.explanation }}
    </blockquote> -->
  </div>
  </div>
  </div>
   <div class="quiz-answer col-md-6">
  <div v-for="(answer, index) in question.answers" :key="index">
  <div
  v-if="index>2 && index<6"
    class="quiz-answer row mr-2 mb-2"
    :key="answer.text"
    :class="answers.includes(index) ? 'checked-option': 'option'"
    :disabled="resolve"
  >
    <button
      class="btn btn-action btn-answer"
      :disabled="resolve"
      @click="toggleAnswer(index)"
      :class="getButtonClass(index)"
    >
      <span class="question-num">{{indexToLetter(index)}}.</span>
      {{ answer.content }}
    </button>

    <!-- <blockquote class="quiz-explanation" v-if="resolve">
      <i class="icon icon-message"></i> {{ answer.explanation }}
    </blockquote> -->
  </div>
  </div>
  </div>
    
<blockquote class="quiz-explanation" v-if="resolve">
      <i class="icon icon-message"></i> {{ question.explanation }}
    </blockquote>
  <div class="nav-question text-right" v-show="!resolve">
    <button class="btn btn-primary" @click="answer">{{ $t('answer') }}</button>
  </div>
</div>
</template>

<script>
export default {
  name: 'DoubleBlank',
  props: ['question', 'resolve', 'sendAnswer'],
  methods: {
    answer() {
      if (!this.answers && this.question.answer && this.question.answer.length) {
        // Answers from previous
        this.sendAnswer(JSON.parse(JSON.stringify(this.question.answer)));
      }

      this.sendAnswer(JSON.parse(JSON.stringify(this.answers.sort())));
      this.answers = [];
    },

    toggleAnswer(index) {
      if (this.answers.includes(index)) {
        this.answers = this.answers.filter(item => item !== index);
      } else {
        if (index<3){
          this.answers=this.answers.filter(item=>item>2)
          this.answers.push(index);
        }else if(index>2){
          this.answers=this.answers.filter(item=>item<3)
          this.answers.push(index);
        }
      }
    },

    getButtonClass(index) {
      const cl = [];

      if (this.resolve) {
        cl.push(this.question.resolution.includes(index) ? 'option-correct' : 'option-wrong');
      }

      // TODO fix for previous
      if (this.question.answer && this.question.answer.includes(index)) {
        cl.push('checked-option');

        if (this.resolve) {
          cl.push(this.question.resolution.includes(index) ? 'checked-option-correct' : 'checked-option-wrong');
        }
      }

      return cl.join(' ');
    },
  },
  mounted() {
    console.log(this.answers)
    this.firstArray = [this.question.answers[0], this.question.answers[1],this.question.answers[2]];
    this.secondArray = [this.question.answers[3], this.question.answers[4],this.question.answers[5]];
    this.thirdArray = [this.question.answers[6], this.question.answers[7],this.question.answers[8]];

},
  data() {
    return {
      answers: [],
      firstArray: [],
      secondArray: [],
      thirdArray: [],
    };
  },
};
</script>

<style scoped>

</style>
