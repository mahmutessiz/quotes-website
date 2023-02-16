<script>
import TheBestQuotes from "../data/TheBestQuotes.json";
import SunTzu from "../data/SunTzu.json";

export default {
  data() {
    return {
      theBestQuotes: TheBestQuotes,
      sunTzu: SunTzu,
      i: 0,
      j: 10,
      x: 0,
      y: 10,
    };
  },
  methods: {
    spliceParamFuncNext() {
      this.i = 10;
      this.j = 20;
    },
    spliceParamFuncPrev() {
      this.i = 0;
      this.j = 10;
    },
    spliceParamFuncPrevSun() {
      this.x = 0;
      this.y = 10;
    },
    spliceParamFuncNextSun() {
      this.x = 10;
      this.y = 20;
    },
  },
  computed: {
    theBestQuotesSplice() {
      let splicedArray = this.theBestQuotes.slice(this.i, this.j);
      return splicedArray;
    },
    sunTzuSplice() {
      let splicedArray = this.sunTzu.slice(this.x, this.y);
      return splicedArray;
    },
  },
};
</script>
<template>
  <main class="flex w-full flex-col items-center bg-gray-900 px-4 py-9">
    <div
      class="flex w-fit flex-wrap justify-center gap-4 transition-all duration-500"
    >
      <h2
        class="w-full text-center text-2xl font-bold text-white underline underline-offset-8 opacity-80"
      >
        The Best Quotes
      </h2>
      <ul
        class="flex w-60 flex-col items-center justify-center gap-4 rounded-lg px-9 py-9 text-center shadow-md shadow-slate-700 odd:bg-gradient-to-tl odd:from-red-800 odd:to-red-400 even:bg-gradient-to-tr even:from-slate-800 even:to-slate-400"
        v-for="bestQuote in theBestQuotesSplice"
        :key="bestQuote"
      >
        <li class="font-bold">&ldquo; {{ bestQuote.quote }} &rdquo;</li>

        <li class="font-mono italic">{{ bestQuote.author }}</li>
      </ul>
      <div class="mt-9 flex w-full justify-around bg-slate-700 px-9">
        <button
          class="cursor-pointer text-lg font-bold text-white"
          @click="spliceParamFuncPrev"
        >
          Prev
        </button>
        <button
          class="cursor-pointer text-lg font-bold text-white"
          @click="spliceParamFuncNext"
        >
          Next
        </button>
      </div>
    </div>
    <br />
    <hr />
    <br /><br />

    <div
      class="flex w-fit flex-wrap justify-center gap-4 transition-all duration-500"
    >
      <h2
        class="w-full text-center text-2xl font-bold text-white underline underline-offset-8 opacity-80"
      >
        Sun Tzu Quotes
      </h2>
      <ul
        class="flex w-60 flex-col items-center justify-center gap-4 rounded-lg px-9 py-9 text-center shadow-md shadow-slate-700 odd:bg-gradient-to-tl odd:from-red-800 odd:to-red-400 even:bg-gradient-to-tr even:from-slate-800 even:to-slate-400"
        v-for="sun in sunTzuSplice"
        :key="sun"
      >
        <li class="font-bold">&ldquo; {{ sun.quote }} &rdquo;</li>
      </ul>
      <div class="mt-9 flex w-full justify-around bg-slate-700 px-9">
        <button
          class="cursor-pointer text-lg font-bold text-white"
          @click="spliceParamFuncPrevSun"
        >
          Prev
        </button>
        <button
          class="cursor-pointer text-lg font-bold text-white"
          @click="spliceParamFuncNextSun"
        >
          Next
        </button>
      </div>
    </div>
  </main>
</template>
