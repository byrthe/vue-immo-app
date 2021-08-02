<template>
  <Layout>
    <h2 class="mb-8 text-4xl font-bold text-center capitalize">
      Cards Section : <span class="text-gray-700">{{ section }}</span>
    </h2>
    <Filter v-model="section" />
    <List :posts="posts" />
  </Layout>
</template>

<script>
import Layout from "./components/Layout.vue"
import Filter from "./components/Filter.vue"
import List from "./components/List.vue"

import data from "./posts.json"
//import data from "https://becodeimmo.herokuapp.com/predict"

export default {
  components: {
    Layout,
    Filter,
    List,
  },
  data() {
    return {
      section: "home",
      posts: data.posts,
    }
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

