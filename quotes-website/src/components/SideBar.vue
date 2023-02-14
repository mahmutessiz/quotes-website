<script>
import categoriData from "../data/categories.json";

export default {
  data() {
    return {
      categoriData: categoriData,
    };
  },
};
</script>
<template>
  <aside class="bg-gray-900">
    <div class="h-fit bg-gray-800 pb-9 text-center">
      <h2
        class="bg-green-900 py-2 font-bold text-white underline opacity-80 shadow-md"
      >
        Categories
      </h2>
      <ul class="flex flex-wrap items-center justify-center">
        <li
          v-for="categori in categoriData.categories"
          :key="categori"
          class="m-4 h-fit cursor-pointer rounded-md bg-lime-500 p-4 text-center font-bold shadow-lg even:bg-blue-400"
        >
          {{ categori }}
        </li>
      </ul>
    </div>
  </aside>
</template>
