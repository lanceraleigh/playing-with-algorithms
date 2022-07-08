<template>
  <h1>The sum of your odds</h1>
  <h3>Input how many odd numbers you want to test (less than 10,000)</h3>
  <form
    action=""
    @submit.prevent="
      clearInitialOdd();
      nSquaredOdds(parseInt(this.input), 10);
    "
  >
    <label for="odds">Input the N value: </label>
    <input type="text" id="odds" v-model="input" />
    <input type="submit" />
  </form>
  <p>Sum of all odds up to the place of {{ input }}: {{ solution }}</p>
  <p class="minimize"><strong>All Odds:</strong> {{ oddArray }}</p>
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
      if (n < 10000) {
        for (let i = 0; i <= n; i++) {
          this.oddArray.push(this.initialOdd);
          this.initialOdd = this.initialOdd + 2;
        }
      } else {
      }
    },
    clearInitialOdd() {
      this.initialOdd = 1;
      this.oddArray = [];
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
