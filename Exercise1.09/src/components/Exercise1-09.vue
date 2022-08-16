<template>
  <div>
    <h1> Looping through an array of objects of your favorite things</h1>
    <ul>
      <li v-for="(item, n) in interests" :key="n">
        {{ item.title }}
        <ol>{{ item.favorite[0] }}</ol>
        <ol>{{ item.favorite[1] }}</ol>

        <!-- to access the inner array in the object property -->
        <ol>
          <li v-for="(fav, m) in item.favorite" :key="m">{{ fav }}</li>
        </ol>
      </li>

      <!-- <li>{{ item.favorite }}</li> -->
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      interests: [
        {
          title: 'Reading',
          favorite: ['Purple Hibiscus', 'Homegoing'],
        },
        {
          title: 'Photography',
          favorite: ['Film'],
        },
        {
          title: 'Writing',
          favorite: ['Creative'],
        },
      ],
    }
  }
}
</script>

<style lang="scss" scoped>
h1 {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  color: #2c3e50;
  margin-top: 60px;
}

li {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  color: #2c3e50;
  margin-top: 0px;

  +li {
    margin-top: 10px;
  }
}

ul {
  padding-left: 0;

  >li {
    max-width: 200px;
    background: #e9e9e9;
    padding: 10px;
    border-radius: 10px;
    margin: 10px 10px 10px 0px;
    list-style: none;
  }
}

ol {
  margin-top: 4px;
  padding: 10px;
  padding-left: 20px;
}
</style>
