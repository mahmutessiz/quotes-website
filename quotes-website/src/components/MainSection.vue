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
    coppyToClipboard(event) {
      // Copy the text inside the text field
      navigator.clipboard.writeText(event.target.innerHTML);
      // Alert the copied text
      console.log("Copied the text: " + event.target.innerHTML);

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
  <main class="flex w-full flex-col items-center bg-gray-900 px-4 py-9">
    <!-- The best quotes section -->
    <div
      class="flex w-fit flex-wrap justify-center gap-4 transition-all duration-500"
    >
      <h2
        class="w-full text-center text-2xl font-bold text-white underline underline-offset-8 opacity-80"
      >
        The Best Quotes
      </h2>
      <ul
        class="flex w-60 flex-col items-center justify-center gap-4 rounded-lg px-9 py-9 text-center shadow-md shadow-slate-700 transition-all duration-500 odd:bg-gradient-to-tl odd:from-green-800 odd:to-green-400 even:bg-gradient-to-tr even:from-blue-800 even:to-blue-400 hover:scale-110"
        v-for="bestQuote in theBestQuotesSplice"
        :key="bestQuote"
        @click="coppyToClipboard"
      >
        <li class="font-bold">&ldquo; {{ bestQuote.quote }} &rdquo;</li>

        <li class="font-mono italic">{{ bestQuote.author }}</li>
      </ul>

      <div class="mt-9 flex w-full justify-end gap-4 bg-slate-900 px-9">
        <p class="text-gray-300">page: {{ pageNumber }}</p>
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

    <!-- quote with bg-image -->

    <div
      class="relative mb-9 grid w-full place-items-center shadow-md shadow-slate-600"
    >
      <div
        class="absolute z-10 grid h-full w-full place-items-center bg-slate-800 bg-opacity-20 text-center font-mono text-xl font-bold text-white backdrop-blur-sm"
      >
        <p class="text-sm sm:text-xl">
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
        class="w-full text-center text-2xl font-bold text-white underline underline-offset-8 opacity-80"
      >
        Sun Tzu Quotes
      </h2>
      <ul
        class="flex w-60 flex-col items-center justify-center gap-4 rounded-lg px-9 py-9 text-center shadow-md shadow-slate-700 transition-all duration-500 odd:bg-gradient-to-tl odd:from-green-800 odd:to-green-400 even:bg-gradient-to-tr even:from-blue-800 even:to-blue-400 hover:scale-110"
        v-for="sun in sunTzuSplice"
        :key="sun"
        @click="coppyToClipboard"
      >
        <li class="font-bold">&ldquo; {{ sun.quote }} &rdquo;</li>
      </ul>

      <div class="mt-9 flex w-full justify-end gap-4 bg-slate-900 px-9">
        <p class="text-gray-300">page: {{ pageNumberSun }}</p>
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

      <!-- quote with bg-image -->
      <div
        class="relative mb-9 grid w-full place-items-center shadow-md shadow-slate-600"
      >
        <div
          class="absolute z-10 grid h-full w-full place-items-center bg-slate-800 bg-opacity-20 text-center font-mono text-xl font-bold text-white backdrop-blur-sm"
        >
          <p class="text-sm sm:text-xl">
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
      class="fixed bottom-8 right-9 hidden w-1/2 place-items-center rounded-md bg-blue-900 py-4 px-2 transition-all duration-500"
    >
      <p class="text-center font-semibold text-white">
        The quote copied to clipboard
      </p>
    </div>
  </main>
</template>
