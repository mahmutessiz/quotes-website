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
  <aside class="bg-slate-100">
    <div class="h-fit bg-rose-700 text-center shadow-md shadow-black/10">
      <h2 class="bg-rose-900 py-2 font-bold text-zinc-100 underline shadow-md">
        Categories
      </h2>
      <ul class="flex flex-wrap items-center justify-center">
        <li
          v-for="categori in categoriData.categories"
          :key="categori"
          class="w-full rounded-sm border-r-2 border-b border-black/50 bg-zinc-100 p-4 text-center font-bold duration-200 even:bg-zinc-50 even:text-black hover:scale-95"
        >
          <RouterLink :to="`/category/${categori}`"
            ><p class="h-fit w-full cursor-pointer">
              {{ categori }}
            </p>
          </RouterLink>
        </li>
      </ul>
    </div>
  </aside>
</template>
