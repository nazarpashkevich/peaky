<template>
  <h2>Slots</h2>

  <AboutLayout>
      <template #introduction>
        introduction
      </template>
      <template #about>
        about about
      </template>
      <template #rewards>

      </template>
  </AboutLayout>
</template>

<style></style>
<script>export default {
  components: {}
}
</script>

<script setup>
import AboutLayout from "./../components/about/AboutLayout.vue";
</script>
