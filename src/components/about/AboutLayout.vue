<template>
<div>
  <slot name="introduction"/>
  <slot name="about"/>
  <slot name="rewards">
    Our rewards will be soon!
  </slot>
</div>
</template>

<script>
export default {
  name: "AboutLayout"
}
</script>

<style scoped>

</style>
