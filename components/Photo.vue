<script setup>
  defineProps({
    photo: {
      type: String,
      default: '/'
    },
    orientation: {
      type: String,
      default: 'portrait'
    },
    index: {
      type: Number,
      default: 0
    },
    title: {
      type: String,
      default: 'Amazing photo'
    },
    year: {
      type: Number,
      default: new Date().getFullYear()
    },
  });
</script>

<template>
  <div class="border bg-gray-50 border-gray-800 shadow-md p-2 transform-gpu transform-all ease-in-out duration-300 will-change-transform hover:shadow-lg hover:rotate-2">
    <img width="220" height="340" class="object-cover object-center animate-fade-in" alt=""
    :src="photo"  
    :class="{'w-85 h-125': orientation === 'portrait', 'w-145 h-125': orientation === 'landscape' }">

    <div class="flex font-serif mt-2 justify-between items-center">
      <span class="text-base text-gray-400 inline">
        /0{{ index }}
      </span>
      <span class="text-xl text-gray-800">
        {{ title }}
      </span>
      <div class="font-serif text-right text-base w-full text-gray-400">
        {{  year }}
      </div>
    </div>
  </div>
</template>