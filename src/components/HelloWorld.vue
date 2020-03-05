<template>
<div>

    <img alt="Vue logo" src="../assets/logo.png"  @click="getNumber" style="cursor: pointer">
<div class="container">
  <!-- <button class="b myButton"> hello </button> -->
  <odometer class="c" :value="number" theme="digital" format="(dd)"></odometer>

</div>
<h1> {{ q }} </h1>
</div>
</template>

<script>

import odometer from 'vue-odometer';
import 'odometer/themes/odometer-theme-digital.css';

export default {
  name: 'HelloWorld',
  components: {
      odometer
    },
  data: function () {
   return {
    number:0,
    numbers: [1,2,3,4,5,6,7,8,9,10,11,12,13,14,15],
    q: '',
    qs: [
      'Name one person in the technology industry that inspires you?',
      'What is your favorite technology brand?',
      'What is the first thing or word that pops to your mind when you hear programming?',
      'What is one electronic device that you can not live without?',
      "Name one application in your opinion that made peoples life easier",
      'Do you think Artificial intelligence (A.I.) will replace humans one day?',
      'If you could choose one company to work for, what company would you choose?',
      'How do you think further technological advances will impact your job?',
      'What qualities do you think are the most important in a programmer?',
      'What are your favorite and least favorite technology products, and why?',
      'Name one invention that is ground breaking in your opinion',
      'If you have been funded, what would your startup be about?',
      'What is one movie that you think anticipates the future?',
      'What is your opinion about the current big five companies? and their use of data and privacy?'
    ],
   }
  },
  methods: {
    getNumber() {
      let n = Math.floor(Math.random() * this.qs.length);
      this.q = this.qs[n];
      this.number = this.numbers[Math.floor(Math.random() * this.numbers.length)];
      this.numbers = this.numbers.filter(n => n != this.number);
    },
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.container {
  display: flex;
    flex-direction: column;
    width:180px;
    margin:auto;
}
.c {
  font-size: 4.7em;
    margin-top: 80px;

}

</style>
