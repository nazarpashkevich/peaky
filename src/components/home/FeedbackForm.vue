<script>
export default {
  data: () => ({
    email: null
  }),
  methods: {
    submitForm: function (event) {
      event.preventDefault();

      // some submit actions

      this.$emit('feedback-sent', this.email)
    }
  },
  emits: ['feedback-sent']
}
</script>
<script setup lang="ts">

</script>

<template>
  <form action="" class="flex flex-col w-64 mx-auto my-auto" v-on:submit="submitForm">
    <input type="email" placeholder="Your email!" class="border rounded-sm mb-4 p-2" required v-model="email">
    <textarea placeholder="Your text" class="border rounded-sm mb-4 p-2" required></textarea>
    <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">Send</button>
  </form>
</template>
