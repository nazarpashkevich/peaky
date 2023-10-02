<template>
  <div class="grid grid-cols-1 lg:grid-cols-2 xl:grid-cols-3 gap-8">
    <template v-for="cat in this.catList">
      <div class="border rounded-lg flex">
        <div class="w-1/3 flex justify-center align-center m-4">
          <div v-bind:style="{ backgroundImage: 'url(' + cat.picture + ')' }"
               class="h-28 w-28 rounded-full bg-cover" alt=""></div>
        </div>
        <div class="w-2/3 px-2 my-auto mx-2">
          <span class="text-xl"> {{ cat.name }}</span>
          <p>{{ cat.description }}</p>
        </div>
      </div>
    </template>
  </div>
</template>

<script>
export default {
  name: "CatList",
  props: {
    limit: {
      type: Number,
      required: false,
      default: 5
    }
  },
  data: () => ({
    catNames: ["Галактико", "Марсик", "Космо", "Звёздочка", "Лунтик", "Астро", "Небула", "Сириус", "Гравити",
      "Плутон", "Спейси", "Солнцекот", "Алиен", "Комета", "Галаксис", "Стеллар", "Небесный", "Космокотик",
      "Полярис", "Юпитер"],
    catDescriptions: [
      "Исследует новые галактики и собирает звёзды.",
      "Обитает на Марсе и любит красные песчаные дюны.",
      "Вечно мечтает о загадочных космических приключениях.",
      "Сверкает ярче любой звезды в небе.",
      "Исследует лунные кратеры и считает звёзды на небе.",
      "Смело летает в космосе и не боится черной дыры.",
      "Скрыт в облаках небулы и создаёт новые звёзды.",
      "Является лучшим другом человека и верным спутником в космосе."
    ],
    catList: []
  }),
  methods: {
    initCatList() { // api dont allow get {n} cats by the one request
      for (let index = 0; index < this.limit; index++) {
        fetch('https://cataas.com/cat?json=true').then(async apiCat => {
          const data = await apiCat.json();
          this.catList.push({
            name: this.getRandomCatName(),
            description: this.getCatDescription(index),
            picture: 'https://cataas.com/c/' + data._id
          })
        });
      }
    },
    getRandomCatName() {
      return this.catNames[Math.floor(Math.random() * this.catNames.length)]
    },
    getCatDescription(index) {
      return this.catDescriptions[index]
    }
  },
  created() {
    this.initCatList()
  }
}
</script>
