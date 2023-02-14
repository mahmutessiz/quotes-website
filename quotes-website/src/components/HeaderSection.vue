<script></script>

<template>
  <header
    class="flex w-full items-center justify-around bg-lime-800 px-4 py-2 shadow-md"
  >
    <div>
      <img
        src="https://picsum.photos/100/50"
        alt="logo"
        class="cursor-pointer"
      />
    </div>
    <div class="flex gap-2">
      <input
        type="text"
        class="w-60 rounded-lg border border-black bg-transparent shadow-md"
        placeholder="   Search a person"
      />
    </div>
    <nav>
      <ul class="mr-4 flex gap-4">
        <li
          class="cursor-pointer p-3 font-bold duration-500 hover:text-black hover:text-opacity-50"
        >
          Home
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
