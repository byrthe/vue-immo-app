<template>
  <Layout>
    <Newform></Newform>
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
// import Form from "./components/Form.vue"
import Newform from "./components/Newform.vue"


// import data from "./posts.json"
//import data from "https://becodeimmo.herokuapp.com/predict"

import * as Vue from 'vue' // in Vue 3
import axios from 'axios'
import VueAxios from 'vue-axios'

export default {
  components: {
    Layout,
    // Form,
    Newform
  },
  data() {
    return {
      section: "home",
      type: '',
    }
  },
  methods: {
    
  },
  // mounted() {
  //   axios.post("https://bappimmo.herokuapp.com/predict", this.posts)
  //   .then(response => console.warn(response));
    // axios.post("https://bappimmo.herokuapp.com/predict", {"type": "APARTMENT","room_number":5,"area": 50,"kitchen_equipped":1,"furnished":0,"fireplace": 0,
    //  "terrace":1,"terrace_area":18,"garden":1,"garden_area":20,"land_surface":120,"facade_count":4,"swimming_pool":0,"building_condition": "GOOD","Province":"BRUXELLES"})
    // .then(response => console.log(response));
  //},
  //   axios.post("https://bappimmo.herokuapp.com/predict", {"type": "APARTMENT","room_number":5,"area": 50,"kitchen_equipped":1,"furnished":0,"fireplace": 0,
  //    "terrace":1,"terrace_area":18,"garden":1,"garden_area":20,"land_surface":120,"facade_count":4,"swimming_pool":0,"building_condition": "GOOD","Province":"BRUXELLES"})
  //   .then(response => console.log('hey this is the response' + response));
  // },
  //   axios.post("https://cors-anywhere.herokuapp.com/https://becodeimmoapp.herokuapp.com/predict", {"type": "APARTMENT","room_number":5,"area": 50,"kitchen_equipped":1,"furnished":0,"fireplace": 0,
  //    "terrace":1,"terrace_area":18,"garden":1,"garden_area":20,"land_surface":120,"facade_count":4,"swimming_pool":0,"building_condition": "GOOD","Province":"BRUXELLES"})
  //   .then(response => console.log(response.post));
  // },
//   }
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

