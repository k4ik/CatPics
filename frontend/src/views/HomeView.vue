<script setup>
import { ref, onMounted } from 'vue';
import SoundButton from '../components/SoundButton.vue';
import Message from '../components/Message.vue';

const image = ref('')
const message = ref('')
const status = ref('')

const getPictures = async () => {
  try {
    const response = await fetch('https://api.thecatapi.com/v1/images/search');
    const data = await response.json();

    image.value = data[0]["url"];
  } catch(e) {
      message.value = e.message;
      status.value = "error";
  }
}

onMounted(() => {
  getPictures();
})
</script>

<template>
  <Message :message="message" :status="status" />
  <main class="linear h-screen w-screen flex justify-center items-center">
    <div class="max-w-[520px] w-full p-[20px] bg-[var(--cold-turkey)] flex-col items-center rounded-[24px] shadow-lg">
        <img :src="image" alt="" class="w-full h-[400px] object-cover mb-20px rounded-[18px] shadow-xs" />
      <div class="flex justify-center items-center mt-[20px]">
        <SoundButton />
        <button @click="getPictures" class="h-[44px] bg-[var(--bazaar)] w-[120px] flex items-center justify-center mx-4 hover:bg-[var(--kabul)] transition duration-400 ease-in-out">
          <img src="../assets/images/refresh.png" alt="refresh" class="w-[20px] h-[20px]" />
        </button>
        <button class="h-[44px] bg-[var(--bazaar)] w-[44px] flex items-center justify-center rounded-full hover:bg-[var(--kabul)] transition duration-400 ease-in-out">
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

