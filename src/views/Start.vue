<template>
  <div>
    <div
      class="quiz-start quiz-intro"
      v-for="(quiz, index) in quizes"
      :key="index"
    >
      <h2>{{ quiz.name }}</h2>

      <div class="quiz-description col-7 col-sm-auto">
        {{ quiz.description }}
      </div>

      <div class="quiz-nav">
        <button
          class="btn btn-primary btn-quiz-start"
          @click="$emit('start', quiz.type)"
        >
          {{ $t("start_quiz") }}
        </button>
      </div>
      <hr />
    </div>
  </div>
</template>

<script>
export default {
  name: "Start",
  props: ["quiz"],
  data() {
    return {
      quizes: [
        {
          name: "Gre Verbal Mixed Sentences",
          type: "sentences",
          description:
            "A time based section (20Qs / 30min) consisting of GRE style questions of mixed category.",
        },
        {
          name: "Gre Verbal Single Blank Sentences",
          description: "A time based section (20Qs / 30min) consisting of GRE style questions of single blank category.",
          type: "fb",
        },
        {
          name: "Gre Verbal Double blank Sentences",
          description: "A time based section (20Qs / 30min) consisting of GRE style questions of double blank category.",
          type: "db",
        },
        {
          name: "Gre Verbal Triple blank Sentences",
          description: "A time based section (20Qs / 30min) consisting of GRE style questions of triple blank category.",
          type: "tb",
        },
        {
          name: "Gre Verbal Sentence Equivalence",
          description: "A time based section (20Qs / 30min) consisting of GRE style questions of sentence equivalence category.",
          type: "se",
        },
      ],
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
