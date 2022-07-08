<template>
  <h1>The sum of your odds</h1>
  <h3>Input how many odd numbers you want to test</h3>
  <form
    action=""
    @submit.prevent="
      clearFibSequence();
      nSquaredOdds(parseInt(this.input), 10);
    "
  >
    <label for="odds">Input the N value: </label>
    <input type="text" id="odds" v-model="input" />
    <input type="submit" />
  </form>
  <p>Sum of all odds up to the place of {{ input }}: {{ solution }}</p>
  <p class="minimize">All Odds: {{ oddArray }}</p>
  <!-- <button
    @click="
      clearFibSequence();
      fibSeq();
    "
  >
    sub
  </button> -->
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      input: "",
      solution: 0,
      oddArray: [],
      initialOdd: 1,
    };
  },
  methods: {
    nSquaredOdds(n) {
      this.solution = n * n;
      for (let i = 0; i <= n; i++) {
        this.oddArray.push(this.initialOdd);
        this.initialOdd = this.initialOdd + 2;
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
.minimize {
  font-size: 0.75rem;
}
</style>
