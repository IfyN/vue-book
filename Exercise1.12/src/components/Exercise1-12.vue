<template>
  <div>
    <h1> Control Data with Vue Lifecycles hook</h1>
    <ul>
      <li v-for="(item, n) in list" :key="n">
        {{ item }}
        <a @click="deleteItem(item)"></a>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      list: ["Game of Thrones", "Billions", "Handmaids Tale", "Curb Your Enthusiasm", "Abbott Elementary", "This is Us", "Emily in Paris"]
    }

  },
  methods: {
    deleteItem(value) {
      this.list = this.list.filter(item => item !== value)
    }
  },
  beforeCreate() {
    alert('beforeCreate: data is static, thats it')
  },
  created() {
    alert('created: data and events ready, but no DOM')
  },
  beforeMount() {
    alert('beforeMount: $el not ready')
  },
  mounted() {
    alert('mounted: DOM ready to use')
  },
  beforeUpdate() {
    alert('beforeUpdate: we know an update is about to happen, and have the data')
  },
  updated() {
    alert('updated: virtual DOM will update after you click OK')
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
