<template>
  <div>
    <h1> Control Data with Vue Lifecycles hook</h1>
    <ul>
      <li v-for="(item, n) in lists" :key="n">
        {{ item }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      lists: ["Game of Thrones", "Billions", "Handmaids Tale", "Curb Your Enthusiasm", "Abbott Elementary", "This is Us", "Emily in Paris"]
    }

  },
  beforeCreate() {
    alert('beforeCreate: data is static, thats it')
  },
  created() {
    alert('created: data and events ready, but no DOM')
  },

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
  padding: 5px 10px;
  border-radius: 10px;
  font-size: 10px;
  color: white;
  text-transform: uppercase;
  text-decoration: none;
}
</style>
