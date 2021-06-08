<template>
  <div id="app">
    <div class="preloader" v-show="$store.state.loader">
      <div class="loadingio-spinner-spinner-4szxh0x31na">
        <div class="ldio-hgxv9qsm58p">
          <div></div>
          <div></div>
          <div></div>
          <div></div>
          <div></div>
          <div></div>
          <div></div>
          <div></div>
          <div></div>
          <div></div>
          <div></div>
          <div></div>
        </div>
      </div>
    </div>
    <div v-show="!$store.state.loader">
      <header-bar></header-bar>
      <div id="quiz">
        <router-view />
      </div>
    </div>
    <Footer></Footer>
  </div>
</template>
<script>
import HeaderBar from "./views/parts/HeaderBar.vue";
import Footer from "./views/parts/Footer.vue";
export default {
  components: {
    HeaderBar,
    Footer,
  },
  
  data() {
    return {
      checkInternetConnection:navigator.onLine,
      loader: false,
    };
  },
  methods: {},
  created() {
    if(!navigator.onLine){
      window.open(window.location.origin+'/static/index.html',"_self")
    }
  },
};
</script>


<style>
@import "./../node_modules/spectre.css/dist/spectre.min.css";

@keyframes ldio-hgxv9qsm58p {
  0% {
    opacity: 1;
  }

  100% {
    opacity: 0;
  }
}

.ldio-hgxv9qsm58p div {
  left: 94px;
  top: 48px;
  position: absolute;
  animation: ldio-hgxv9qsm58p linear 1s infinite;
  background: #93dbe9;
  width: 12px;
  height: 24px;
  border-radius: 6px / 12px;
  transform-origin: 6px 52px;
}

.ldio-hgxv9qsm58p div:nth-child(1) {
  transform: rotate(0deg);
  animation-delay: -0.9166666666666666s;
  background: #93dbe9;
}

.ldio-hgxv9qsm58p div:nth-child(2) {
  transform: rotate(30deg);
  animation-delay: -0.8333333333333334s;
  background: #93dbe9;
}

.ldio-hgxv9qsm58p div:nth-child(3) {
  transform: rotate(60deg);
  animation-delay: -0.75s;
  background: #93dbe9;
}

.ldio-hgxv9qsm58p div:nth-child(4) {
  transform: rotate(90deg);
  animation-delay: -0.6666666666666666s;
  background: #93dbe9;
}

.ldio-hgxv9qsm58p div:nth-child(5) {
  transform: rotate(120deg);
  animation-delay: -0.5833333333333334s;
  background: #93dbe9;
}

.ldio-hgxv9qsm58p div:nth-child(6) {
  transform: rotate(150deg);
  animation-delay: -0.5s;
  background: #93dbe9;
}

.ldio-hgxv9qsm58p div:nth-child(7) {
  transform: rotate(180deg);
  animation-delay: -0.4166666666666667s;
  background: #93dbe9;
}

.ldio-hgxv9qsm58p div:nth-child(8) {
  transform: rotate(210deg);
  animation-delay: -0.3333333333333333s;
  background: #93dbe9;
}

.ldio-hgxv9qsm58p div:nth-child(9) {
  transform: rotate(240deg);
  animation-delay: -0.25s;
  background: #93dbe9;
}

.ldio-hgxv9qsm58p div:nth-child(10) {
  transform: rotate(270deg);
  animation-delay: -0.16666666666666666s;
  background: #93dbe9;
}

.ldio-hgxv9qsm58p div:nth-child(11) {
  transform: rotate(300deg);
  animation-delay: -0.08333333333333333s;
  background: #93dbe9;
}

.ldio-hgxv9qsm58p div:nth-child(12) {
  transform: rotate(330deg);
  animation-delay: 0s;
  background: #93dbe9;
}

.loadingio-spinner-spinner-4szxh0x31na {
  width: 200px;
  height: 200px;
  display: inline-block;
  overflow: hidden;
  background: rgba(NaN, NaN, NaN, 0);
}

.ldio-hgxv9qsm58p {
  width: 100%;
  height: 100%;
  position: relative;
  transform: translateZ(0) scale(1);
  backface-visibility: hidden;
  transform-origin: 0 0;
  /* see note above */
}

.ldio-hgxv9qsm58p div {
  box-sizing: content-box;
}

.preloader {
  align-items: center;
  background: white;
  display: flex;
  height: 100vh;
  justify-content: center;
  left: 0;
  position: fixed;
  top: 0;
  transition: opacity 0.3s linear;
  width: 100%;
  z-index: 9999;
}
.img-wrapper {
  display: flex;
  justify-content: center;
}
.img-cls {
  width: 200px;
}
.filter-loader {
  -webkit-filter: blur(8px);
  -moz-filter: blur(8px);
  -ms-filter: blur(8px);
  -o-filter: blur(8px);
  filter: blur(8px);
}
#app {
  font-family: Roboto, Helvetica, Arial, sans-serif;
}
/* Simple CSS for the Quiz */
#quiz {
  font-family: "Open Sans", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  -webkit-box-shadow: 0 0.25rem 0.75rem rgba(0, 0, 0, 0.05);
  box-shadow: 0 0.25rem 0.75rem rgba(0, 0, 0, 0.05);
  margin: 10px auto;
  padding: 15px 20px;
  line-height: 1.4rem;
  max-width: 960px;
}

/* spectre.css overwrites */
.btn.disabled,
.btn:disabled,
.btn[disabled] {
  opacity: 0.8;
}

/* quiz-nav */
.quiz-nav {
  margin: 10px 0;
}

.quiz-nav .btn {
  margin-right: 10px;
}

.quiz-answers {
  margin: 35px 0;
}

/* Buttons (Answers) */
.bytee-quiz .btn-answer {
  display: block;
  width: 100%;
  margin: 5px 0;
  text-align: center;
  position: relative;
  overflow: hidden;
  height: 2rem;
}

.question-num {
  position: absolute;
  left: 0;
  top: 0;
  height: 100%;
  width: 30px;
  background: #5755d9;
  border-radius: 0 15px 15px 0 / 0 20px 20px 0;
  margin-left: 0;
  padding: 0 5px;
  color: #fff;
}

.question-num:before {
  content: "";
  display: inline-block;
  height: 100%;
  vertical-align: middle;
}

.bytee-quiz .option-correct {
  border: 1px solid #36bf42;
}

.bytee-quiz .option-wrong {
  border: 1px solid #ef251c;
}

.bytee-quiz .checked-option,
.bytee-quiz .checked-option .btn-answer {
  background: #5755d9;
  color: #fff;
}

.bytee-quiz .checked-option-correct .question-num,
.bytee-quiz .option-correct .question-num {
  background: #36bf42;
}

.bytee-quiz .checked-option-wrong .question-num,
.bytee-quiz .option-wrong .question-num {
  background: #ef251c;
}

.bytee-quiz .checked-option-wrong {
  border: 2px solid #ef251c;
  background: #d98484;
}

.bytee-quiz .checked-option-correct {
  border: 2px solid #36bf42;
  background: #6ed97b;
}

/* Suggest */
.suggestion-answer {
  margin: 5px 0;
  padding: 10px;
  border: 1px solid #ccc;
}

/* Some responsive improvements */
/* Portrait and Landscape */
@media only screen and (max-device-width: 812px) {
  #quiz {
    border: 0;
    padding: 5px;
    margin: 0 auto;
  }

  .btn-primary {
    display: block;
    margin: 5px 0;
  }

  .btn {
    width: 100%;
  }
}
</style>
