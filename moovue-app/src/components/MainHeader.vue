<template>
  <header
    class="flex flex-col sm:flex-row m-5 justify-between items-center text-center h-auto"
  >
    <div class="flex flex-grow justify-evenly max-w-2xl">
      <router-link
        to="/"
        class="flex flex-col items-center cursor-pointer group w-12 sm:w-20 hover:dark:text-white"
      >
        <HomeIcon class="h-8 mb-1 group-hover:animate-bounce" />
        <p class="opacity-100 group-hover:opacity-100 tracking-widest">Home</p>
      </router-link>
      <router-link
        to="/list"
        class="flex flex-col items-center cursor-pointer group w-12 sm:w-20 hover:dark:text-white"
      >
        <EyeIcon class="h-8 mb-1 group-hover:animate-bounce" />
        <p class="opacity-100 group-hover:opacity-100 tracking-widest">
          Ma liste
        </p>
      </router-link>
      <router-link
        to="/likes"
        class="flex flex-col items-center cursor-pointer group w-12 sm:w-20 hover:dark:text-white"
      >
        <HeartIcon class="h-8 mb-1 group-hover:animate-bounce" />
        <p class="opacity-100 group-hover:opacity-100 tracking-widest">
          Favoris
        </p>
      </router-link>
      <router-link
        to="/profil"
        class="flex flex-col items-center cursor-pointer group w-12 sm:w-20 hover:dark:text-white"
      >
        <UserIcon class="h-8 mb-1 group-hover:animate-bounce" />
        <p class="opacity-100 group-hover:opacity-100 tracking-widest">
          Profil
        </p>
      </router-link>
      <h1
        class="text-4xl font-extrabold leading-none tracking-tight md:text-5xl lg:text-6xl dark:text-white"
      >
        MooVue
      </h1>
      <DarkMode />
    </div>
  </header>
</template>

<script>
import DarkMode from "@/components/DarkMode.vue";
import {
  HomeIcon,
  UserIcon,
  HeartIcon,
  EyeIcon,
} from "@heroicons/vue/24/outline";

export default {
  name: "MainHeader",
  components: {
    DarkMode,
    HomeIcon,
    UserIcon,
    HeartIcon,
    EyeIcon,
  },
};
</script>
