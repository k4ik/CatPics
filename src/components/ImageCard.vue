<template>
    <div class="max-w-80 w-full flex flex-col items-center bg-white py-4 rounded-2xl shadow-2xl">
        <img :src="imageUrl" alt="image cat" class="w-72 h-72 object-cover mb-4" v-show="imageUrl">
        <form @submit.prevent>
            <button class="h-auto px-4 py-1 rounded-lg bg-green-500" @click="getImages">Generate pictures</button>
        </form>
    </div>
</template>

<script>
    export default {
        name: "ImageCard",
        methods: {
            async getImages() {
                const req = await fetch("https://api.thecatapi.com/v1/images/search");
                const data = await req.json();

                this.imageUrl = data[0].url;
            }
        },
        data(){
            return {
                imageUrl: ""
            }
        }
    }
</script>