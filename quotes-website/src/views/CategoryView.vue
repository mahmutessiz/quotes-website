<script>
import { useRoute } from "vue-router";
import CategoryData from "../data/categories.json";
import CategoryQuotes from "../data/categoryQuotes.json";
import NotFoundView from "./NotFoundView.vue";
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
    return (this.pathData = path);
  },
  methods: {
    coppyToClipboard(event) {
      // Copy the text inside the text field
      navigator.clipboard.writeText(event.target.innerHTML);

      // alert box for copy
      const alertContainer = document.querySelector("#alert-copy");
      alertContainer.classList.add("grid");
      alertContainer.classList.remove("hidden");
      setTimeout(() => {
        alertContainer.classList.add("hidden");
        alertContainer.classList.remove("grid");
      }, 2000);
    },
  },
  computed: {
    machesData() {
      return this.categoryData.categories.includes(this.pathData);
    },
  },
  components: { NotFoundView },
};
</script>

<template>
  <div
    class="grid min-h-screen place-items-center bg-zinc-200 py-4"
    v-if="machesData == true"
  >
    <h2
      class="text-2xl font-bold text-black underline underline-offset-8 opacity-80"
    >
      {{ pathData }}
    </h2>
    <ul class="flex flex-wrap justify-center gap-4 p-4">
      <li
        class="flex w-60 flex-col items-center justify-center gap-4 rounded-lg px-9 py-9 text-center shadow-md shadow-slate-700 transition-all duration-300 odd:bg-gradient-to-tl odd:from-zinc-50 odd:to-zinc-300 even:bg-gradient-to-tr even:from-gray-900 even:to-black even:text-zinc-200/90 hover:scale-105"
        v-for="categoryQuote in categoryQuotes"
        :key="categoryQuote"
        @click="coppyToClipboard"
      >
        {{ categoryQuote }}
      </li>
    </ul>
  </div>

  <div v-else class="grid min-h-screen place-items-center">
    <NotFoundView />
  </div>
  <div
    id="alert-copy"
    class="fixed bottom-8 hidden w-1/2 place-items-center rounded-md bg-blue-900 py-4 px-2 transition-all duration-500 sm:bottom-8 sm:right-9"
  >
    <p class="text-center font-semibold text-white">
      The quote copied to clipboard
    </p>
  </div>
</template>
