<script setup lang="ts">
import SuccessIcon from "@/assets/images/icon-success.svg";
type Props = {
  email: string;
};
defineProps<Props>();
</script>

<template>
  <div class="success">
    <img class="success-icon" :src="SuccessIcon" alt="success icon" />
    <div class="success-content">
      <h1>thanks for subscribing</h1>
      <p>
        Thanks for subscribing! A confirmation email has been sent to
        <strong>{{ email }}</strong> Please open it and click the button inside
        to confirm your subscription.
      </p>
    </div>
    <button @click="$emit('dismiss')">Dismiss message</button>
  </div>
</template>

<style lang="css" scoped>
.success {
  width: 100%;
  height: 100dvh;
  background-color: white;
  max-width: 100%;
  max-height: 100%;
  display: flex;
  padding: 4rem 2rem;
  flex-direction: column;
  .success-content {
    margin-top: 3rem;
    margin-bottom: 3rem;
  }
  .success-icon {
    width: 4rem;
  }
  h1 {
    font-size: clamp(2rem, 5vw, 4rem);
    margin-bottom: 2rem;
  }
  p {
    font-size: clamp(1.6rem, 5vw, 1.8rem);
  }
  button {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
    background-color: var(--dark-slate-grey);
    border-radius: 1rem;
    color: var(--white);
    font-size: 1.4rem;
    font-weight: 700;
    transition: background 0.3s ease-in-out;
    border: none;
    padding: 1rem;
    margin-top: auto;
    &:hover {
      cursor: pointer;
      background: rgb(217, 85, 85);
      background: linear-gradient(
        90deg,
        rgba(217, 85, 85, 1) 55%,
        rgba(255, 21, 0, 1) 100%
      );
    }
  }
}

@media screen and (min-width: 768px) {
  .success {
    max-width: 40rem;
    margin: 0 auto;
    border-radius: 1rem;
    padding: 4rem;
    .success-icon {
      width: 8rem;
    }
  }
}
</style>
