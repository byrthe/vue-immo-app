<template>
  <Layout>
    <Form></Form>
    <hr>
    <!-- <h2 class="mb-8 text-4xl font-bold text-center capitalize">
      Cards Section : <span class="text-gray-700">{{ section }}</span>
    </h2>
    <Filter v-model="section" />
    <List :posts="posts" /> -->
  </Layout>
</template>

<script>
import Layout from "./components/Layout.vue"
import Filter from "./components/Filter.vue"
import List from "./components/List.vue"
import Form from "./components/Form.vue"


import data from "./posts.json"
//import data from "https://becodeimmo.herokuapp.com/predict"

// import axios from "axios"
import axios from 'axios';
// const api = import.meta.env.VITE_NYT_API_KEY

export default {
  components: {
    Layout,
    Filter,
    List,
    Form
  },
  data() {
    return {
      section: "home",
      posts: data.posts,

      type: '',
    }
  },
  methods: {
    // Helper function for extracting a nested image object
    extractImage(post) {
      const defaultImg = {
        url: "http://placehold.it/210x140?text=N/A",
        caption: post.title,
      }
      if (!post.multimedia) {
        return defaultImg
      }
      let imgObj = post.multimedia.find(
        media => media.format === "mediumThreeByTwo210"
      )
      return imgObj ? imgObj : defaultImg
    },
    async fetchNews() {
      try {
        const url = `https://api.nytimes.com/svc/topstories/v2/${this.section}.json?api-key=${api}`
        const response = await axios.get(url)
        const results = response.data.results
        this.posts = results.map(post => ({
          title: post.title,
          abstract: post.abstract,
          url: post.url,
          thumbnail: this.extractImage(post).url,
          caption: this.extractImage(post).caption,
          byline: post.byline,
          published_date: post.published_date,
        }))
      } catch (err) {
        if (err.response) {
          // client received an error response (5xx, 4xx)
          console.log("Server Error:", err)
        } else if (err.request) {
          // client never received a response, or request never left
          console.log("Network Error:", err)
        } else {
          console.log("Client Error:", err)
        }
      }
    },
  },
  mounted() {
    // this.fetchNews()
    axios.post("https://cors-anywhere.herokuapp.com/https://becodeimmoapp.herokuapp.com/predict", {"type": "APARTMENT","room_number":5,"area": 50,"kitchen_equipped":1,"furnished":0,"fireplace": 0,
     "terrace":1,"terrace_area":18,"garden":1,"garden_area":20,"land_surface":120,"facade_count":4,"swimming_pool":0,"building_condition": "GOOD","Province":"BRUXELLES"})
    .then(response => console.log(response));
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
}
</style>

