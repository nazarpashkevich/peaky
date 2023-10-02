<script setup lang="ts" xmlns="http://www.w3.org/1999/html">
import MainMenu from './components/MainMenu.vue'
import BottomMenu from './components/BottomMenu.vue'
import AuthBlock from './components/AuthBlock.vue'
</script>

<template>
  <header>
    <div class="w-full h-20 bg-slate-500 flex px-8 lg:px-24">
      <a href="/" class="my-auto">
        <img src="./assets/images/logo.png" class="w-56"/>
      </a>
      <MainMenu class="ml-24 mr-auto hidden lg:block"/>
      <AuthBlock class="ml-auto my-auto"/>
    </div>
  </header>

  <RouterView/>

  <footer>
    <div class="w-full h-auto bg-slate-500 flex px-24">
      <img src="./assets/images/logo.png" class="my-auto w-28 h-full h-8"/>
      <BottomMenu class="ml-60 mr-auto w-auto h-full"/>
    </div>
  </footer>
</template>
