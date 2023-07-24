<template>
 <header class="w-full fixed py-6 top-0 bg-gray-50/10 backdrop-blur-md">
    <div class="flex mx-auto w-full px-4 items-center justify-between xl:w-screen-xl xl:px-0">

      <nuxt-link to="">
        <svg 
          class="h-8 w-8"
          fill="currentColor"
          viewBox="0 0 20 20"
          xmlns="http://www.w3.org/2000/svg"
          >
            <path
              fill-rule="evenodd"
              d="M10 18a8 8 0 100-16 8 8 0 000 16zM7 9a1 1 0 000 2h6a1 1 0 100-2H7z"
              clip-rule="evenodd">
            </path>
        </svg>
      </nuxt-link>

      <nav class="flex gap-4">
        <NuxtLink to="/" class="font-serif text-gray-800">Home</NuxtLink>
        <NuxtLink to="/works" class="font-serif text-gray-800">Works</NuxtLink>
      </nav>
    </div>
 </header>
</template>