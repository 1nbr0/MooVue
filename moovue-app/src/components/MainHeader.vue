<template>
  <header>
    <h1>This is the header</h1>
    <h1
      class="text-4xl font-extrabold leading-none tracking-tight md:text-5xl lg:text-6xl dark:text-white"
    >
      MooVue
    </h1>
    <DarkMode />
  </header>
</template>

<script>
import DarkMode from "./DarkMode.vue";

export default {
  name: "MainHeader",
  components: {
    DarkMode,
  },
};
</script>
