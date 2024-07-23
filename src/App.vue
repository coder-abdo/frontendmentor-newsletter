<script setup lang="ts">
import { ref } from "vue";
import NewsletterEmail from "@/components/NewsletterEmail.vue";
import NewsletterBackground from "@/components/NewsletterBackground.vue";
import SuccessMessage from "@/components/SuccessMessage.vue";

const error = ref(false);
const email = ref("");
const isSuccess = ref(false);
const handleSubmit = () => {
  const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
  console.log(email.value);
  if (emailRegex.test(email.value)) {
    error.value = false;
    isSuccess.value = true;
  } else {
    error.value = true;
    isSuccess.value = false;
  }
};
const handleDismiss = () => {
  isSuccess.value = false;
  email.value = "";
  error.value = false;
};
</script>

<template>
  <main>
    <div v-if="!isSuccess" class="main">
      <NewsletterEmail
        :email="email"
        @update:email="email = $event"
        :error="error"
        @submit="handleSubmit"
      />
      <NewsletterBackground />
    </div>
    <SuccessMessage v-else @dismiss="handleDismiss" />
  </main>
</template>

<style scoped>
main {
  height: 100%;
  width: 100%;
}
.main {
  display: flex;
  flex-direction: column-reverse;
  border-radius: 2%;
  background-color: var(--white);
  padding: 2rem;
}
@media screen and (min-width: 768px) {
  .main {
    flex-direction: row;
    max-width: 80%;
    width: 100%;
    height: 100%;
    margin: 0 auto;
  }
}
</style>
