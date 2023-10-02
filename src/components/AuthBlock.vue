<script>
export default {
  data: () => ({})
}
</script>
<script setup>
import { UserIcon } from '@heroicons/vue/24/solid'

</script>

<template>
  <div class="auth-block hidden xl:flex">
    <a class="mx-4 text-center justify-center h-full inline-flex items-center text-gray-100 hover:cursor-pointer">
      Login
    </a>
    <a class="mx-4 text-center justify-center h-full inline-flex items-center text-gray-100 hover:cursor-pointer
   whitespace-nowrap">
      Sign Up
    </a>
  </div>
  <div class="flex justify-center items-center ml-auto xl:hidden">
    <UserIcon class="h-8 w-8 text-white"/>
  </div>
</template>
