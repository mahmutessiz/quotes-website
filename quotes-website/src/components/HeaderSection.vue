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
    class="z-20 flex w-full items-center justify-center gap-4 bg-lime-800 px-4 py-2 shadow-md md:justify-around"
  >
    <div>
      <router-link to="/"
        ><img
          src="../assets/3872631364_create_a_logo_for_quotes_website.png"
          alt="logo"
          class="hidden cursor-pointer self-start sm:block"
      /></router-link>
    </div>
    <nav>
      <ul class="mr-4 flex gap-4">
        <RouterLink to="/"
          ><li
            class="cursor-pointer p-3 text-sm font-bold text-neutral-50 duration-500 hover:text-neutral-100 hover:text-opacity-50 active:text-white sm:text-base"
          >
            Home
          </li></RouterLink
        >
        <router-link to="/category"
          ><li
            class="cursor-pointer p-3 text-sm font-bold text-neutral-50 duration-500 hover:text-neutral-100 hover:text-opacity-50 sm:text-base md:hidden"
          >
            Categories
          </li>
        </router-link>
        <li
          class="hidden cursor-pointer p-3 font-bold text-neutral-50 duration-500 hover:text-neutral-100 hover:text-opacity-50 md:block"
        >
          <a href="https://github.com/mahmutessiz" target="_blank">Github</a>
        </li>
        <li
          class="hidden cursor-pointer p-3 font-bold text-neutral-50 duration-500 hover:text-neutral-100 hover:text-opacity-50 md:block"
        >
          <a
            href="https://www.linkedin.com/in/mahmut-e%C5%9Fsiz-b1b8a8185/"
            target="_blank"
            >Linkedin</a
          >
        </li>
        <li
          class="hidden cursor-pointer p-3 font-bold text-neutral-50 duration-500 hover:text-neutral-100 hover:text-opacity-50 md:block"
        >
          <a href="https://mahmutessiz-portfolio.vercel.app/" target="_blank"
            >Portfolio</a
          >
        </li>
        <li
          class="cursor-pointer rounded-md bg-blue-400 p-3 text-sm font-bold shadow-md duration-500 hover:text-black hover:text-opacity-50 sm:text-base"
        >
          <a href="mailto:mahmutessiz71@gmail.com">Contact</a>
        </li>
      </ul>
    </nav>
  </header>
</template>
