<script>
import categoriData from "../data/categories.json";
import { RouterLink } from "vue-router";

export default {
  data() {
    return {
      categoriData: categoriData,
      RouterLink,
    };
  },
};
</script>

<template>
  <div class="grid min-h-screen justify-center bg-gray-800">
    <div class="h-fit max-w-lg bg-gray-800 pb-9 text-center">
      <ul class="flex flex-wrap items-center justify-center">
        <li
          v-for="categori in categoriData.categories"
          :key="categori"
          class="m-4 h-fit cursor-pointer rounded-md bg-lime-500 p-4 text-center font-bold shadow-lg even:bg-blue-400"
        >
          <RouterLink :to="`/category/${categori}`"> {{ categori }}</RouterLink>
        </li>
      </ul>
    </div>
  </div>
</template>
