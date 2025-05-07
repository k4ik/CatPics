<script setup>
import SoundButton from '../components/SoundButton.vue';
</script>

<template>
  <main class="linear h-screen w-screen flex justify-center items-center">
    <div class="max-w-[520px] w-full p-[20px] bg-[var(--cold-turkey)] flex-col items-center rounded-[24px] shadow-lg">
        <img src="../assets/images/cat.jpeg" alt="" class="w-full max-h-[400px] object-cover mb-20px rounded-[18px] shadow-xs" />
      <div class="flex justify-center items-center mt-[20px]">
        <SoundButton />
        <button class="h-[44px] bg-[var(--bazaar)] w-[120px] flex items-center justify-center mx-4 hover:bg-[var(--kabul)] transition duration-400 ease-in-out">
          <img src="../assets/images/refresh.png" alt="refresh" class="w-[20px] h-[20px]" />
        </button>
        <button class="h-[44px] bg-[var(--bazaar)] w-[44px] flex items-center justify-center rounded-full hover:bg-[var(--kabul)] transtiion duration-400 ease-in-out">
          <img src="../assets/images/star.png" alt="star" class="w-[20px] h-[20px]" />
        </button>
      </div>
    </div>
  </main>
</template>

<style scoped>
.linear {
  background: linear-gradient(130deg, var(--bazaar), #987c7c);
}
</style>

