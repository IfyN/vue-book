<template>
  <div>

    <h1>Returning Shopping Cart Data with Vue methods</h1>
    <div>Cart({{ totalItems }}) {{ formatCurrency(totalCost) }}</div>
    <ul>
      <li v-for="n in 5" :key="n">
        <a href="#" @click="addToCart(n)">Add {{ formatCurrency(n) }}</a>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      totalCost: 0,
      totalItems: 0,
    }
  },

  methods: {
    addToCart(n) {
      this.totalCost = this.totalCost + 1,
        this.totalItems = this.totalItems + n
    },

    formatCurrency(currVal) {
      return `₦${currVal.toFixed(2)}`
    }
  }



}
</script>

<style lang="scss" scoped>
ul {
  padding-left: 0;
}

li {
  display: block;
  list-style: none;

  +li {
    margin-top: 10px;
  }
}

a {
  display: inline-block;
  background: rgb(235, 50, 50);
  border-radius: 10px;
  font-size: 10px;
  color: white;
  padding: 5px 10px;
  text-decoration: none;
}
</style>
