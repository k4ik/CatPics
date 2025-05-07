<script setup>
import { ref, nextTick } from 'vue';
const audio = ref(null);
const audioSource = ref('');

const paths = [
  new URL("../assets/audio/cat1.wav", import.meta.url).href,
  new URL("../assets/audio/cat2.wav", import.meta.url).href,
  new URL("../assets/audio/cat3.wav", import.meta.url).href,
  new URL("../assets/audio/cat4.wav", import.meta.url).href,
  new URL("../assets/audio/cat5.wav", import.meta.url).href
];

const playSound = async () => {
  const random = Math.floor(Math.random() * paths.length);
  audioSource.value = paths[random];
  await nextTick();
  audio.value.play();
};
</script>

<template>
  <button @click="playSound" class="bg-[var(--bazaar)] w-[44px] h-[44px] rounded-full flex items-center justify-center hover:bg-[var(--kabul)] transition duration-400 ease-in-out">
    <img src="../assets/images/pets.png" alt="cat paw" class="w-[20px] h-[20px]" />
  </button>

  
  <audio :src="audioSource" ref="audio" />
  </template>
