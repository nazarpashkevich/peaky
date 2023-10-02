<script>
export default {
  data: () => ({
    characterList: [
      {
        name: "Thomas Shelby",
        description: "Thomas Michael ‘Tommy’ Shelby OBE DCM MM MP is the main protagonist of the Peaky Blinders",
        picture: "https://focus.independent.ie/thumbor/4Gb2trRUxYLirgM1fmq6Dv8WiJk=/203x33:1755x889/960x640/prod-mh-ireland/c2e70d08-c450-11ed-aa5d-0210609a3fe2.png"
      },
      {
        name: "Grace Shelby",
        description: "Grace Helen Shelby (née Burgess) is an Irish woman who takes up employment as a barmaid at The Garrison Pub, and secretly operates as an undercover agent for the Birmingham Police",
        picture: "https://metro.co.uk/wp-content/uploads/2020/06/PRI_154740850.jpg?quality=90&strip=all"
      },
      {
        name: "Arthur Shelby",
        description: "Arthur Shelby Jr. is one of the main protagonists of the Peaky Blinders. He is the eldest son",
        picture: "https://hips.hearstapps.com/hmg-prod/images/arthur-shelby-in-peaky-blinders-season-6-1646316779.jpg?crop=0.646xw:0.431xh;0.228xw,0.137xh&resize=1200:*"
      },
      {
        name: "John Shelby",
        description: "John Michael Shelby (also known as Johnny and John Boy) is one of the two former tritagonists (alongside Polly Gray) of Peaky Blinders",
        picture: "https://www.nme.com/wp-content/uploads/2020/04/joe-cole-peaky-blinders-696x442.jpg"
      },
      {
        name: "Polly Gray",
        description: "Elizabeth Pollyanna \"Polly\" Gray (née Shelby) is one of the two former tritagonists",
        picture: "https://i.pinimg.com/originals/bb/e8/00/bbe800a9ed0719b918086700f383acbe.png"
      }
    ],
    favouriteList: [],
    showFavouriteList: true
  }),
  methods: {
    addToFavourite(index) {
      const newFavourite = this.characterList[index]
      !this.favouriteList.some(e => e.name === newFavourite.name) ? this.favouriteList.push(newFavourite) : false
    }
  }
}
</script>
<script setup>
import FavouriteList from './FavouriteList.vue'
</script>

<template>
  <div class="my-12 mx-12 xl:mx-36">
    <h2 class="text-center text-3xl">Main Characters</h2>
    <div class="mt-12 grid grid-cols-1 lg:grid-cols-2 xl:grid-cols-3 gap-8">
      <template v-for="(character, index) in characterList">
        <div class="border rounded-lg">
          <div class="m-4 flex flex-col">
            <div v-bind:style="{ backgroundImage: 'url(' + character.picture + ')' }"
                 class="w-48 sm:w-64 h-48 sm:h-64 bg-cover rounded-full mx-auto bg-center"></div>
            <div class="flex flex-col mt-4 text-center mb-4">
              <span class="mx-auto text-xl mb-4">{{ character.name }}</span>
              <p class="mx-2">{{ character.description }}</p>
            </div>
            <button class="mx-auto px-4 py-2 bg-slate-400 text-white mt-auto rounded-lg"
                    v-on:click="addToFavourite(index)">
              Add to favourite
            </button>
          </div>
        </div>
      </template>
    </div>
    <FavouriteList :characterList="favouriteList"/>
  </div>
</template>
