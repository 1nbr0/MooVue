<template>
  <MainHeader />
  <router-view />
</template>

<script>
import MainHeader from "./components/MainHeader.vue";

export default {
  name: "App",
  components: {
    MainHeader,
  },
};
</script>

<style>
html.dark {
  color-scheme: dark;
}

body {
  @apply bg-slate-50 text-slate-800 dark:bg-slate-800 dark:text-slate-50;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

nav {
  padding: 30px;
}

nav a {
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}
</style>
