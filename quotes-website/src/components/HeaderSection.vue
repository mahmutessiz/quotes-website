<script></script>

<template>
  <header
    class="w-full bg-lime-800 flex justify-between items-center px-4 py-2 shadow-md"
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
        class="bg-transparent border-black border shadow-md w-60 rounded-lg"
        placeholder="   Search a person"
      />
      <img
        src="https://picsum.photos/30/30"
        class="cursor-pointer rounded-lg shadow-lg"
        alt="search"
      />
    </div>
    <nav>
      <ul class="flex gap-4 mr-4">
        <li
          class="bg-blue-400 shadow-md font-bold hover:text-black hover:text-opacity-50 duration-500 p-3 rounded-md cursor-pointer"
        >
          Contact
        </li>
      </ul>
    </nav>
  </header>
</template>
