<script>
export default {
  data: () => ({
    items: [

    ]
  })
}
</script>
<script setup lang="ts">

</script>

<template>
  <div class="my-8 flex flex-col">
    <div class="w-80 hidden xl:block">
  <template v-for="item in items">
    <a :href="item.link" class="m-1 text-center h-full inline-flex items-center text-gray-100">
      {{ item.title }}
    </a>
  </template>
    </div>
  </div>
</template>
