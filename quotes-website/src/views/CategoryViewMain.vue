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
          class="h-fit w-full cursor-pointer rounded-sm border-r-2 border-b border-black/50 bg-zinc-100 p-4 text-center font-bold duration-200 even:bg-zinc-200/80 even:text-black hover:scale-95"
        >
          <RouterLink :to="`/category/${categori}`"> {{ categori }}</RouterLink>
        </li>
      </ul>
    </div>
  </div>
</template>
