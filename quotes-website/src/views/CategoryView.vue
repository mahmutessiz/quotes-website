<script>
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
    /* parameter name detection */
    const path = useRoute().params.id;

    /* I'm not proud for this */

    if (path == "Inspiration") {
      this.categoryQuotes = CategoryQuotes.Inspiration;
    } else if (path == "Motivation") {
      this.categoryQuotes = CategoryQuotes.Motivation;
    } else if (path == "Love") {
      this.categoryQuotes = CategoryQuotes.Love;
    } else if (path == "Life") {
      this.categoryQuotes = CategoryQuotes.Life;
    } else if (path == "Success") {
      this.categoryQuotes = CategoryQuotes.Success;
    } else if (path == "Wisdom") {
      this.categoryQuotes = CategoryQuotes.Wisdom;
    } else if (path == "Happiness") {
      this.categoryQuotes = CategoryQuotes.Happiness;
    } else if (path == "Gratitude") {
      this.categoryQuotes = CategoryQuotes.Gratitude;
    } else if (path == "Creativity") {
      this.categoryQuotes = CategoryQuotes.Creativity;
    } else if (path == "Determination") {
      this.categoryQuotes = CategoryQuotes.Determination;
    } else if (path == "Empowerment") {
      this.categoryQuotes = CategoryQuotes.Empowerment;
    } else if (path == "Friendship") {
      this.categoryQuotes = CategoryQuotes.Friendship;
    } else if (path == "Humor") {
      this.categoryQuotes = CategoryQuotes.Humor;
    } else if (path == "Leadership") {
      this.categoryQuotes = CategoryQuotes.Leadership;
    } else if (path == "Overcoming Adversity") {
      this.categoryQuotes = CategoryQuotes["Overcoming Adversity"];
    } else if (path == "Peace") {
      this.categoryQuotes = CategoryQuotes.Peace;
    } else if (path == "Perseverance") {
      this.categoryQuotes = CategoryQuotes.Perseverance;
    } else if (path == "Positive Thinking") {
      this.categoryQuotes = CategoryQuotes["Positive Thinking"];
    } else if (path == "Strength") {
      this.categoryQuotes = CategoryQuotes.Strength;
    } else if (path == "Courage") {
      this.categoryQuotes = CategoryQuotes.Courage;
    }

    /* console.log(path); */
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
  <div
    class="grid min-h-screen place-items-center bg-gray-900 py-4"
    v-if="machesData == true"
  >
    <h2
      class="text-2xl font-bold text-white underline underline-offset-8 opacity-80"
    >
      {{ pathData }}
    </h2>
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

  <div v-else class="grid min-h-screen place-items-center">
    <h2>page not found</h2>
  </div>
</template>
