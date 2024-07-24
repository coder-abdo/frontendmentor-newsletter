<script setup lang="ts"></script>

<template>
  <div class="newsletter-background">
    <img
      src="../assets/images/illustration-sign-up-desktop.svg"
      alt="newsletter background"
      sizes="(max-width: 768px) 100vw, (min-width: 769px) 50vw"
      srcset="
        ../assets/images/illustration-sign-up-mobile.svg   400w,
        ../assets/images/illustration-sign-up-desktop.svg 1000w
      "
    />
  </div>
</template>

<style scoped>
.newsletter-background {
  width: 100%;
  max-height: 30rem;
  padding: 0;
  overflow-y: hidden;
}
img {
  height: 100%;
  width: 100%;
  object-fit: cover;
  border-radius: 1rem;
  aspect-ratio: 0.67;
}
@media screen and (min-width: 768px) {
  .newsletter-background {
    height: 100%;
    padding: 2rem;
    max-height: 100%;
    flex-basis: 50%;
  }
}
</style>
