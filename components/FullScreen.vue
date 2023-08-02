<script setup>
  defineProps({
    url:{
      type: String,
      default: ''
    },
    title: {
      type: String,
      default: ''
    },
    orientation: {
      type: String,
      default: ''
    },
    index: {
      type: Number,
      default: 0
    },
    year: {
      type: Number,
      default: new Date().getFullYear()
    },
  });
</script>

<template>
 <teleport to='body'>
  <div class="flex h-screen bg-dark-800/90 w-full top-0 left-0 z-30 overflow-scroll backdrop-blur-md fixed flex items-center justify-center">
    <div class="flex h-full relative items-center justify-center animate-fade-in">
      <div class="overflow-scroll relative">
        <img 
          :src="url" class="object-cover object-center"
          :class="{
            'h-10/12 w-11/12 mx-auto xl:w-320 xl:h-220': orientation === 'landscape',
            'h-10/12 w-11/12 mx-auto xl:w-220 xl:h-160': orientation === 'portrait'}" alt="">
        <div class="flex mt-2 px-4 justify-between items-center sm:px-10 xl:px-0">
          <span class="text-base text-gray-500 inline">/0{{ index }}</span>
          <span class="text-xl text-gray-50/70 inline">{{ title }}</span>
        </div>
        <div class="text-right text-base w-full px-4 text-gray-500 sm:px-10 xl:px-0">
          {{ year }}
        </div>
      </div>
    </div>
  </div>
 </teleport>
</template>

