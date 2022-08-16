<template>
  <div>
    <h1>My interests </h1>
    <ul>
      <li v-for="(item, n) in interests" :key="n">
        <!--n is the loop index and item outputs array string-->
        {{ item }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      interests: ['reading', 'photography', 'writing'],
    }
  }
}

</script>

<style lang="scss" scoped>
li {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  color: #2c3e50;
  margin-top: 10px;
}

h1 {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
