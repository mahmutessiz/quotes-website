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
  <main class="w-full flex justify-center items-center p-9 bg-gray-900">
    <div class="w-fit flex flex-wrap justify-center gap-4">
      <h2
        class="w-full text-center font-bold text-2xl text-white opacity-80 underline-offset-8 underline"
      >
        The Best Quotes
      </h2>
      <br />
      <br />
      <ul
        class="w-60 rounded-lg shadow-md shadow-slate-700 even:from-slate-800 even:bg-gradient-to-tr even:to-slate-400 odd:from-red-800 odd:to-red-400 odd:bg-gradient-to-tl px-9 py-9 items-center text-center justify-center flex flex-col gap-4"
        v-for="bestQuote in theBestQuotes"
        :key="bestQuote"
      >
        <li class="font-bold">&ldquo; {{ bestQuote.quote }} &rdquo;</li>

        <li class="italic font-mono">{{ bestQuote.author }}</li>
      </ul>
    </div>
  </main>
</template>
