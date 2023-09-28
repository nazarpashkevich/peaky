<script>
export default {
  data: () => ({
    title: "Vue example site",
    description: "This is my vue example site for improve and levelup practical skills with Vue.js",
    picture: "https://r4.wallpaperflare.com/wallpaper/503/928/982/pink-floyd-animals-london-pigs-wallpaper-a72e6150550802cbe65ff47912d762b7.jpg"
  })
}
</script>
<script setup lang="ts">

</script>

<template>
  <div class="h-[42rem] bg-cover bg-center p-12" :style="{ backgroundImage: 'url(' + picture + ')' }">
    <div class="relative h-full">
      <div class="bg-slate-400 rounded-lg opacity-20 h-full"></div>
      <div class="absolute top-1/3 left-5 xl:left-20">
        <div class="text-6xl xl:text-7xl text-indigo-50">{{ title }}</div>
        <div class="text-xl mt-8 xl:ml-8 text-indigo-50">{{ description }}</div>
      </div>
    </div>
  </div>
</template>
