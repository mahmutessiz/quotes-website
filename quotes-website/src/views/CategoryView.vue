<script>
import { findProp } from "@vue/compiler-core";
import { useRoute } from "vue-router";
import CategoryData from "../data/categories.json";
import CategoryQuotes from "../data/categoryQuotes.json";
export default {
  data() {
    return {
      categoryData: CategoryData,
      categoryQuotes: CategoryQuotes,
      pathData: "",
    };
  },
  beforeMount() {
    const path = useRoute().params.id;
    if (path == "Inspiration") {
      this.categoryQuotes = CategoryQuotes.Inspiration;
    }

    console.log(path);
    return (this.pathData = path);
  },
  computed: {
    machesData() {
      return this.categoryData.categories.includes(this.pathData);
    },
  },
};
</script>

<template>
  <div class="grid place-items-center" v-if="machesData == true">
    <h1>{{ pathData }}</h1>
    <ul class="flex flex-wrap justify-center gap-4 p-4">
      <li
        class="flex w-60 flex-col items-center justify-center gap-4 rounded-lg px-9 py-9 text-center shadow-md shadow-slate-700 odd:bg-gradient-to-tl odd:from-red-800 odd:to-red-400 even:bg-gradient-to-tr even:from-slate-800 even:to-slate-400"
        v-for="categoryQuote in categoryQuotes"
        :key="categoryQuote"
      >
        {{ categoryQuote }}
      </li>
    </ul>
  </div>

  <div v-else>
    <h2>page not found</h2>
  </div>
</template>
