<script>
export default {
  props: {
    characterList: {
      type: Array,
      required: true
    }
  },
  methods: {
    removeFromFavourites(index) {
      this.characterList.splice(index, 1)
    }
  },
  computed: {
    favouritesCount() {
      return this.characterList.length
    }
  }
}
</script>
<script setup lang="ts">

</script>

<template>
  <div class="my-12 mx-12 xl:mx-36">
    <div v-show="favouritesCount" class="mt-8">
      <h2 class="text-center text-2xl">Favourite list</h2>
      <p>Ypu have {{ favouritesCount }} favourite items</p>
      <ul class="list-disc">
        <li v-for="(favourite, index) in characterList" v-on:click="removeFromFavourites(index)">
          {{ favourite.name }}
        </li>
      </ul>
    </div>
  </div>
</template>
