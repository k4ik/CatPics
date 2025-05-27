<script setup>
import { ref, onMounted } from 'vue';
import Message from '../components/Message.vue';
const images = ref([]);
const message = ref('');
const status = ref('');

const getImages = async () => {
  try {
    const response = await fetch(`http://localhost:8000/api/image/saved/`, {
      method: 'GET',
      headers: {
        'Content-Type': 'application/json'
      }
    })

    if (!response.ok) {
      message.value = "Failed to get images";
      status.value = "error";
    }

    const data = await response.json();
    images.value = data;
  } catch (e) {
    message.value = e.message;
    status.value = "error";
  }
}
</script>

<template>
  <main>
    <h1>Your Saved Pictures</h1>
    <div>
      <img v-for="(image, id) in images" :src="image" :alt="id" />
    </div>
  </main>
</template>
