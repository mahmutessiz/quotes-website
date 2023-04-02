<script>
import { RouterLink } from "vue-router";
export default {
  data() {
    return {
      RouterLink,
    };
  },
};
</script>

<template>
  <header
    class="z-20 flex w-full items-center justify-center gap-4 bg-black px-4 py-2 text-zinc-200 shadow-md md:justify-around"
  >
    <nav>
      <ul class="mr-4 flex gap-4">
        <RouterLink to="/"
          ><li
            class="cursor-pointer border-r p-3 text-sm font-bold duration-300 hover:text-zinc-400 sm:text-base"
          >
            Home
          </li></RouterLink
        >
        <router-link to="/category"
          ><li
            class="cursor-pointer border-r p-3 text-sm font-bold duration-300 hover:text-zinc-400 sm:text-base md:hidden"
          >
            Categories
          </li>
        </router-link>
        <li
          class="hidden cursor-pointer border-r p-3 font-bold duration-300 hover:text-zinc-400 md:block"
        >
          <a href="https://github.com/mahmutessiz" target="_blank">Github</a>
        </li>
        <li
          class="hidden cursor-pointer border-r p-3 font-bold duration-300 hover:text-zinc-400 md:block"
        >
          <a
            href="https://www.linkedin.com/in/mahmut-e%C5%9Fsiz-b1b8a8185/"
            target="_blank"
            >Linkedin</a
          >
        </li>
        <li
          class="hidden cursor-pointer border-r p-3 font-bold duration-300 hover:text-zinc-400 md:block"
        >
          <a href="https://mahmutessiz.dev/" target="_blank">Portfolio</a>
        </li>
        <li
          class="cursor-pointer rounded-md bg-rose-900 p-3 text-sm font-bold text-white shadow-md duration-500 hover:text-opacity-80 sm:text-base"
        >
          <a href="mailto:mahmutessiz71@gmail.com">Contact</a>
        </li>
      </ul>
    </nav>
  </header>
</template>
