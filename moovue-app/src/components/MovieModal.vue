<template>
  <div
    id="small-modal"
    tabindex="-1"
    class="fixed top-0 left-0 right-0 z-50 hidden w-full p-4 overflow-x-hidden overflow-y-auto md:inset-0 h-modal md:h-full"
  >
    <div class="relative w-full h-full max-w-4xl md:h-auto">
      <!-- Modal content -->
      <div class="relative bg-white rounded-lg shadow dark:bg-gray-700">
        <!-- Modal header -->
        <div
          class="flex items-center justify-between p-5 border-b rounded-t dark:border-gray-600"
        >
          <h3 class="text-xl font-bold text-gray-900 dark:text-white">
            {{ modalData.title }}
          </h3>
          <button
            type="button"
            class="text-gray-400 bg-transparent hover:bg-gray-200 hover:text-gray-900 rounded-lg text-sm p-1.5 ml-auto inline-flex items-center dark:hover:bg-gray-600 dark:hover:text-white"
            data-modal-hide="small-modal"
          >
            <svg
              aria-hidden="true"
              class="w-5 h-5"
              fill="currentColor"
              viewBox="0 0 20 20"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                fill-rule="evenodd"
                d="M4.293 4.293a1 1 0 011.414 0L10 8.586l4.293-4.293a1 1 0 111.414 1.414L11.414 10l4.293 4.293a1 1 0 01-1.414 1.414L10 11.414l-4.293 4.293a1 1 0 01-1.414-1.414L8.586 10 4.293 5.707a1 1 0 010-1.414z"
                clip-rule="evenodd"
              ></path>
            </svg>
            <span class="sr-only">Close</span>
          </button>
        </div>
        <!-- Modal body -->
        <div class="p-6 space-y-6">
          <img
            class="object-cover w-full rounded-t-lg h-96 md:h-auto md:w-48 md:rounded-none md:rounded-l-lg"
            :src="`https://www.themoviedb.org/t/p/w300_and_h450_bestv2${modalData.img}`"
            alt=""
          />

          <p
            class="text-lg font-medium leading-relaxed text-gray-500 dark:text-gray-400"
            style="
              position: absolute;
              top: 17%;
              padding-left: 24%;
              padding-right: 5%;
            "
          >
            {{ modalData.text }}
          </p>

          <div
            class="flex items-center"
            style="position: absolute; top: 75%; padding-left: 32%"
          >
            <p
              class="text-base leading-relaxed font-bold text-gray-500 dark:text-gray-400"
              style="padding-right: 100px"
            >
              Date de sortie : {{ modalData.release_date }}
            </p>
            <svg
              aria-hidden="true"
              class="w-10 h-10 text-yellow-400"
              fill="currentColor"
              viewBox="0 0 20 20"
              xmlns="http://www.w3.org/2000/svg"
            >
              <title>Rating star</title>
              <path
                d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z"
              ></path>
            </svg>
            <p class="ml-2 text-base font-bold text-gray-900 dark:text-white">
              {{ modalData.rate }}/10
            </p>
            <span
              class="w-1 h-1 mx-1.5 bg-gray-500 rounded-full dark:bg-gray-400"
            ></span>
            <p
              class="text-base font-medium text-gray-900 underline hover:no-underline dark:text-white"
            >
              {{ modalData.rateCount }} avis
            </p>
          </div>
        </div>
        <!-- Modal footer -->
        <!--<div class="flex items-center p-6 space-x-2 border-t border-gray-200 rounded-b dark:border-gray-600">
					</div>-->
      </div>
    </div>
  </div>
</template>

<script>
import { Flowbite } from "flowbite";
export default {
  name: "MovieModal",
  props: {
    modalData: Array,
  },
  created: function () {
    Flowbite;
  },
};
</script>
