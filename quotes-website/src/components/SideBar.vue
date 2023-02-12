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
  <aside class="bg-lime-300 text-center">
    <h2 class="py-2 font-bold underline shadow-md bg-amber-500">Categories</h2>
    <ul
      class="h-screen flex flex-wrap items-center justify-center overflow-auto"
    >
      <li
        v-for="categori in categoriData.categories"
        :key="categori"
        class="p-4 m-4 h-fit rounded-md shadow-lg bg-lime-500 text-center cursor-pointer even:bg-blue-400 font-bold"
      >
        {{ categori }}
      </li>
    </ul>
  </aside>
</template>
