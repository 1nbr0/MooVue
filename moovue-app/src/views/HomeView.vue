<template>
  <div class="home">
    <MovieList
      :movies="movies"
      @doSearch="doSearch($event)"
      @modalToggle="modalToggle($event)"
    />
    <MovieModal v-bind:modalData="modalData" />
  </div>
</template>

<script>
// @ is an alias to /src
import MovieList from "@/components/MovieList.vue";
import MovieModal from "@/components/MovieModal.vue";
import axios from "axios";

const apiURL =
  "https://api.themoviedb.org/3/movie/popular?api_key=a8259c59f49d490bc078f6c196279508&language=fr-FR";

export default {
  name: "HomeView",
  components: {
    MovieList,
    MovieModal,
  },
  data() {
    return {
      search: "",
      movies: null,
      modalData: {
        title: null,
        text: null,
        img: null,
        rate: null,
        rateCount: null,
        release_date: null,
      },
    };
  },
  created: function () {
    this.fetchDataAsync();
  },
  methods: {
    doSearch(text) {
      this.search = text;
      this.fetchDataAsync();
    },
    fetchDataAsync: async function () {
      try {
        if (this.search !== "") {
          const apiURL1 =
            "https://api.themoviedb.org/3/search/movie?api_key=a8259c59f49d490bc078f6c196279508&query=" +
            this.search;
          const response = await axios.get(apiURL1);
          console.log(response.data);
          this.movies = response.data.results;
        } else {
          const response = await axios.get(apiURL);
          console.log(response.data);
          this.movies = response.data.results;
        }
      } catch (error) {
        console.log(error);
      }
    },
    modalToggle(movie) {
      this.modalData = {
        title: movie.original_title,
        text: movie.overview,
        img: movie.poster_path,
        rate: movie.vote_average,
        rateCount: movie.vote_count,
        release_date: movie.release_date,
      };
    },
  },
};
</script>
