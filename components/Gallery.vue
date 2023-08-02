<script setup>
  const photos = [
    {url: '/gallery/01.jpg', title: "Title Generic 1", orientation: 'portrait', year: 2023},
    {url: '/gallery/02.jpg', title: "Title Generic 2", orientation: 'portrait', year: 2023},
    {url: '/gallery/03.jpg', title: "Title Generic 3", orientation: 'landscape', year: 2023},
    {url: '/gallery/04.jpg', title: "Title Generic 4", orientation: 'portrait', year: 2023},
    {url: '/gallery/05.jpg', title: "Title Generic 5", orientation: 'landscape', year: 2023},
    {url: '/gallery/06.jpg', title: "Title Generic 6", orientation: 'portrait', year: 2022},
    {url: '/gallery/07.jpg', title: "Title Generic 7", orientation: 'landscape', year: 2022},
    {url: '/gallery/08.jpg', title: "Title Generic 8", orientation: 'portrait', year: 2021},
    {url: '/gallery/09.jpg', title: "Title Generic 9", orientation: 'portrait', year: 2021},
    {url: '/gallery/10.jpg', title: "Title Generic 10", orientation: 'landscape', year: 2020},
    ];

    const isFullScreen = ref(false);
    const currentUrl = ref('');
    const currentTitle = ref('');
    const currentIndex = ref(0);
    const currentYear = ref(null);
    const currentOrientation = ref('');

    function showFullScreen(photo, index) {
      currentUrl.value = photo.url
      currentTitle.value = photo.title
      currentIndex.value = index
      currentYear.value = photo.year
      currentOrientation.value = photo.orientation
      isFullScreen.value = true
    };
</script>
<template>
   <div class="mx-auto w-full px-4 sm:mt-0 xl:w-full xl: px-0">
    <h1 class="font-serif mx-auto max-w-screen-xl mt-20 text-left text-5xl text-gray-800 xl:text-7xl">
      Projet récent
    </h1>
    <div class="flex mt-10 p-10 gap-10 snap-x snap-mandatory relative overflow-x-auto">
      <template v-for="(photo, index) in photos" :key="index">
        <div 
          @click="showFullScreen(photo, index)"
          class="cursor-pointer flex flex-col snap-end overflow-visible shrink-0">
          <!-- Photos -->
          <Photo :index="index+1" :photo="photo.url" :title="photo.title" :orientation="photo.orientation" :year="photo.year" />
        </div>
      </template>
    </div>
    <FullScreen v-if="isFullScreen" :url="currentUrl" :index="currentIndex" :title="currentTitle" :orientation="currentOrientation" :year="currentYear"/>
  </div>
</template>