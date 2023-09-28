<script>
export default {
  data: () => ({
    items: [
      {
        title: "Company",
        link: "/company"
      },
      {
        title: "About Us",
        link: "/abount-us"
      },
      {
        title: "Donates",
        link: "/donates"
      }
    ]
  })
}
</script>
<script setup lang="ts">

</script>

<template>
  <div class="w-full flex">
  <template v-for="item in items">
    <a :href="item.link" class="mx-12 text-center justify-center h-full inline-flex items-center text-gray-100">
      {{ item.title }}
    </a>
  </template>
  </div>
</template>
