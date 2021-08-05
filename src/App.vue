<template>

  <Layout>
    <Newform></Newform>
    <hr>
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
    
  }
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

