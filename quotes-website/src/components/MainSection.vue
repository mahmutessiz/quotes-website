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
  <main class="w-full bg-slate-400 flex justify-center items-center p-9">
    <div class="w-fit bg-white flex flex-wrap justify-center gap-4">
      <h2 class="w-full text-center font-bold text-2xl">The Best Quotes</h2>
      <br />
      <ul
        class="w-60 rounded-lg shadow-md shadow-slate-700 even:from-slate-800 even:bg-gradient-to-tr odd:from-red-800 odd:bg-gradient-to-tl px-9 py-9 items-center text-center justify-center flex flex-col gap-4"
        v-for="bestQuote in theBestQuotes"
        :key="bestQuote"
      >
        <li class="font-bold">"{{ bestQuote.quote }}"</li>

        <li>{{ bestQuote.author }}</li>
      </ul>
    </div>
  </main>
</template>
