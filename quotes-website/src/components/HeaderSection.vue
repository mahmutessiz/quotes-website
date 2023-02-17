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
    class="flex w-full items-center justify-around bg-lime-800 px-4 py-2 shadow-md"
  >
    <div>
      <router-link to="/"
        ><img
          src="../assets/3872631364_create_a_logo_for_quotes_website.png"
          alt="logo"
          class="cursor-pointer"
      /></router-link>
    </div>
    <nav>
      <ul class="mr-4 flex gap-4">
        <RouterLink to="/"
          ><li
            class="cursor-pointer p-3 font-bold text-neutral-50 duration-500 hover:text-neutral-100 hover:text-opacity-50"
          >
            Home
          </li></RouterLink
        >
        <li
          class="cursor-pointer p-3 font-bold text-neutral-50 duration-500 hover:text-neutral-100 hover:text-opacity-50"
        >
          Github
        </li>
        <li
          class="cursor-pointer p-3 font-bold text-neutral-50 duration-500 hover:text-neutral-100 hover:text-opacity-50"
        >
          Linkedin
        </li>
        <li
          class="cursor-pointer p-3 font-bold text-neutral-50 duration-500 hover:text-neutral-100 hover:text-opacity-50"
        >
          Portfolio
        </li>
        <li
          class="cursor-pointer rounded-md bg-blue-400 p-3 font-bold shadow-md duration-500 hover:text-black hover:text-opacity-50"
        >
          Contact
        </li>
      </ul>
    </nav>
  </header>
</template>
