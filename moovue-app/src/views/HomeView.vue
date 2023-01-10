<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <HelloWorld :movies="movies" />
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import axios from 'axios'
const apiURL =
  'https://api.themoviedb.org/3/movie/popular?api_key=a8259c59f49d490bc078f6c196279508'

export default {
  name: 'HomeView',
  components: {
    HelloWorld,
  },
  data() {
    return {
      movies: null,
    }
  },
  created: function () {
    this.fetchDataAsync()
  },

  methods: {
    fetchDataAsync: async function () {
      const response = await axios.get(apiURL)
      console.log(response.data)
      this.movies = response.data.results
    },
  },
}
</script>
