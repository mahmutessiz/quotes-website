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
  <aside>
    <ul
      class="w-1/4 h-screen bg-lime-300 flex flex-wrap justify-center p-9 overflow-auto"
    >
      <li
        v-for="categori in categoriData.categories"
        :key="categori"
        class="w-2/3 p-4 m-4 h-fit rounded-md shadow-lg bg-lime-500 text-center cursor-pointer even:bg-blue-400 font-bold"
      >
        {{ categori }}
      </li>
    </ul>
  </aside>
</template>
