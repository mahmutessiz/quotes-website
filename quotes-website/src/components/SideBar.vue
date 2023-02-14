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
    <div class="bg-gray-800 text-center pb-9 h-fit">
      <h2
        class="py-2 font-bold underline shadow-md bg-green-900 text-white opacity-80"
      >
        Categories
      </h2>
      <ul class="flex flex-wrap items-center justify-center">
        <li
          v-for="categori in categoriData.categories"
          :key="categori"
          class="p-4 m-4 h-fit rounded-md shadow-lg bg-lime-500 text-center cursor-pointer even:bg-blue-400 font-bold"
        >
          {{ categori }}
        </li>
      </ul>
    </div>
  </aside>
</template>
