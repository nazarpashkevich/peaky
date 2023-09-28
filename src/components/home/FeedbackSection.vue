<script>
export default {
  data: () => ({
    isSubmitted: false
  }),
  methods: {
    onFeedbackSent(email) {
      console.log('YUP, email is ' + email)
      this.isSubmitted = true
    }
  }
}
</script>
<script setup>
import FeedbackForm from "@/components/home/FeedbackForm.vue";
</script>

<template>
  <div class="mx-8 my-20 border flex flex-col lg:flex-row lg:h-64 lg:mx-36">
    <div class="text-3xl m-auto" v-if="isSubmitted">We receive your feedback, thank you!</div>
    <template v-else>
        <div class="lg:w-1/2 text-xl text-center justify-center flex flex-col my-4">
          <span class="bold">Share your feedback with us!</span>
          <p>It`s very important for better functional</p>
        </div>
        <div class="lg:w-1/2 flex mb-4">
          <FeedbackForm @feedback-sent="onFeedbackSent"/>
        </div>
    </template>
  </div>
</template>
