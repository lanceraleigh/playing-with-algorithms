<template>
  <form
    action=""
    @submit.prevent="
      clearFibSequence();
      fibSeq();
    "
  >
    <input type="text" v-model="input" />
    <input type="submit" />
  </form>
  <p>Fib: {{ fibSequence }}</p>
  <button
    @click="
      clearFibSequence();
      fibSeq();
    "
  >
    sub
  </button>
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      input: "",
      fibSequence: [0, 1],
      initialI: 1,
    };
  },
  methods: {
    fibSeq() {
      let i = this.initialI;
      let iLess = i - 1;
      let fib = this.fibSequence[i] + this.fibSequence[iLess];
      if (fib < parseInt(this.input, 10)) {
        this.fibSequence.push(fib);
        this.initialI = this.initialI + 1;
        this.fibSeq();
      } else {
        this.initialI = 1;
      }
    },
    clearFibSequence() {
      this.fibSequence = [0, 1];
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
