<template>
  <div class="container">
    <input type="number" v-model="incrementOne" />
    <h3> Get Input: {{ incrementOne }}</h3>
    <h5>Divide by Two: {{ divideByTwo }}</h5>
    <h3> Multiply by Two: {{ multiplyByTwo }}</h3>
  </div>
</template>

<script>
export default {
  data() {
    return {
      count: -1,
      divideByTwo: 0,
      multiplyByTwo: 0
    }
  },
  computed: {
    incrementOne: {
      // getter
      get() {
        return this.count + 1
      },
      // setter
      set(val) {
        this.count = val - 1,
          this.divideByTwo = val / 2,
          this.multiplyByTwo = val * 2
      },
    },
  },
}
</script>

<style>
.container {
  margin: 0 auto;
  padding: 30px;
  max-width: 600px;
}

input {
  padding: 10px 6px;
  margin: 20px 10px 10px 0;
}
</style>
