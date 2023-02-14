<script>
import TheBestQuotes from "../data/TheBestQuotes.json";

export default {
  data() {
    return {
      theBestQuotes: TheBestQuotes,
    };
  },
};
</script>
<template>
  <main class="flex w-full items-center justify-center bg-gray-900 p-9">
    <div class="flex w-fit flex-wrap justify-center gap-4">
      <h2
        class="mb-4 w-full text-center text-2xl font-bold text-white underline underline-offset-8 opacity-80"
      >
        The Best Quotes
      </h2>
      <ul
        class="flex w-60 flex-col items-center justify-center gap-4 rounded-lg px-9 py-9 text-center shadow-md shadow-slate-700 odd:bg-gradient-to-tl odd:from-red-800 odd:to-red-400 even:bg-gradient-to-tr even:from-slate-800 even:to-slate-400"
        v-for="bestQuote in theBestQuotes"
        :key="bestQuote"
      >
        <li class="font-bold">&ldquo; {{ bestQuote.quote }} &rdquo;</li>

        <li class="font-mono italic">{{ bestQuote.author }}</li>
      </ul>
    </div>
  </main>
</template>
