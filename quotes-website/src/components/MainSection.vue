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
      pageNumber: 1,
      pageNumberSun: 1,
    };
  },
  methods: {
    spliceParamFuncNext() {
      this.i = 10;
      this.j = 20;
      this.pageNumber = 2;
    },
    spliceParamFuncPrev() {
      this.i = 0;
      this.j = 10;
      this.pageNumber = 1;
    },
    spliceParamFuncPrevSun() {
      this.x = 0;
      this.y = 10;
      this.pageNumberSun = 1;
    },
    spliceParamFuncNextSun() {
      this.x = 10;
      this.y = 20;
      this.pageNumberSun = 2;
    },
    copyToClipboard(event) {
      // Copy the text inside the text field
      navigator.clipboard.writeText(event.target.innerText);

      // Alert the copied text
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
  <main class="flex w-full flex-col items-center bg-zinc-100 px-4 py-9">
    <!-- The best quotes section -->
    <div
      class="flex w-fit flex-wrap justify-center gap-4 transition-all duration-500"
    >
      <h2
        class="w-full text-center text-2xl font-bold underline underline-offset-8 opacity-80"
      >
        The Best Quotes
      </h2>
      <div class="mt-9 flex w-full justify-end gap-4 bg-zinc-100 px-9">
        <button class="cursor-pointer text-black" @click="spliceParamFuncPrev">
          Prev
        </button>
        <p class="text-sm text-gray-500">{{ pageNumber }}</p>
        <button class="cursor-pointer text-black" @click="spliceParamFuncNext">
          Next
        </button>
      </div>
      <ul
        class="flex w-60 flex-col items-center justify-center gap-4 rounded-lg px-9 py-9 text-center shadow-md shadow-slate-700 transition-all duration-300 odd:bg-gradient-to-tl odd:from-zinc-50 odd:to-zinc-300 even:bg-gradient-to-tr even:from-gray-900 even:to-black even:text-zinc-200/90 hover:scale-105"
        v-for="bestQuote in theBestQuotesSplice"
        :key="bestQuote"
      >
        <li class="font-bold" @click.prevent="copyToClipboard">
          &ldquo; {{ bestQuote.quote }} &rdquo; <br />
          <br />
          <p class="font-mono font-thin italic">{{ bestQuote.author }}</p>
        </li>
      </ul>
    </div>
    <br />
    <br /><br />

    <!-- quote with bg-image -->

    <div
      class="relative mb-9 grid w-full place-items-center shadow-md shadow-slate-600"
    >
      <div
        class="absolute z-10 grid h-full w-full place-items-center bg-opacity-20 text-center font-mono backdrop-blur-sm"
      >
        <p class="text-sm font-bold text-black sm:text-2xl">
          A journey of a thousand miles, <br />
          begins with a single step. <br />
          &ldquo; Sun Tzu &rdquo;
        </p>
      </div>

      <img
        class="opacity-70"
        src="../assets/sunTzubg.png"
        alt="background image far east"
      />
    </div>

    <!-- Sun Tzu quotes -->
    <div
      class="flex w-fit flex-wrap justify-center gap-4 transition-all duration-500"
    >
      <h2
        class="w-full text-center text-2xl font-bold underline underline-offset-8 opacity-80"
      >
        Sun Tzu Quotes
      </h2>
      <div class="mt-9 flex w-full justify-end gap-4 bg-zinc-100 px-9">
        <button
          class="cursor-pointer text-black"
          @click="spliceParamFuncPrevSun"
        >
          Prev
        </button>
        <p class="text-gray-500">{{ pageNumberSun }}</p>

        <button
          class="cursor-pointer text-black"
          @click="spliceParamFuncNextSun"
        >
          Next
        </button>
      </div>
      <ul
        class="flex w-60 flex-col items-center justify-center gap-4 rounded-lg px-9 py-9 text-center shadow-md shadow-slate-700 transition-all duration-300 odd:bg-gradient-to-tl odd:from-zinc-50 odd:to-zinc-300 even:bg-gradient-to-tr even:from-gray-900 even:to-black even:text-zinc-200/90 hover:scale-105"
        v-for="sun in sunTzuSplice"
        :key="sun"
      >
        <li class="font-bold" @click.prevent="copyToClipboard">
          &ldquo; {{ sun.quote }} &rdquo;
        </li>
      </ul>

      <!-- quote with bg-image -->
      <div
        class="relative mb-9 grid w-full place-items-center shadow-md shadow-slate-600"
      >
        <div
          class="absolute z-10 grid h-full w-full place-items-center bg-opacity-20 text-center font-mono backdrop-blur-sm"
        >
          <p class="text-sm font-bold text-black sm:text-2xl">
            A journey of a thousand miles, <br />
            begins with a single step. <br />
            &ldquo; Sun Tzu &rdquo;
          </p>
        </div>

        <img
          class="opacity-70"
          src="../assets/sunTzubg.png"
          alt="background image far east"
        />
      </div>
    </div>
    <div
      id="alert-copy"
      class="fixed bottom-8 z-30 hidden w-1/2 place-items-center rounded-md bg-blue-900 py-4 px-2 transition-all duration-500 sm:bottom-8 sm:right-9"
    >
      <p class="text-center font-semibold text-white">
        The quote copied to clipboard
      </p>
    </div>
  </main>
</template>
