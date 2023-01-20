<template>
  <div>
    <div class="block space-y-4 md:flex md:space-y-0 md:space-x-4">
      <!-- Modal toggle -->
    </div>
    <h1 class="text-5xl font-extrabold dark:text-white text-center pb-10 pt-10">
      Liste des films
    </h1>

    <input
      type="text"
      v-model="search"
      @keyup.enter="doSearch()"
      placeholder="Rechercher un film ..."
    />

    <div class="grid gap-4 grid-cols-2 grid-rows-3">
      <div v-for="movie in movies" :key="movie.id">
        <button
          v-on:click="modalToggle(movie)"
          data-modal-target="small-modal"
          data-modal-toggle="small-modal"
          class="flex flex-col items-center bg-white border rounded-lg shadow-md md:flex-row md:max-w-xl hover:bg-gray-100 dark:border-gray-700 dark:bg-gray-800 dark:hover:bg-gray-700"
          type="button"
        >
          <img
            class="object-cover w-full rounded-t-lg h-96 md:h-auto md:w-48 md:rounded-none md:rounded-l-lg"
            :src="`https://www.themoviedb.org/t/p/w300_and_h450_bestv2${movie.poster_path}`"
            alt=""
          />
          <div class="flex flex-col justify-between p-4 leading-normal">
            <h5
              class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white"
            >
              {{ movie.original_title }}
            </h5>
            <p class="mb-3 font-normal text-gray-700 dark:text-gray-400">
              {{ movie.overview }}
            </p>
          </div>
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    movies: Array,
  },
  data() {
    return {
      search: "",
    };
  },
  methods: {
    doSearch() {
      this.$emit("doSearch", this.search);
    },
  },
};
</script>
