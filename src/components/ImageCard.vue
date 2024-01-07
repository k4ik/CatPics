<template>
    <div class="max-w-80 flex flex-col items-center bg-emerald-500 pt-4">
        <img :src="src" alt="image cat" class="w-72 h-72">
        <form @submit.prevent>
            <button class="h-auto px-4 py-1 my-2 rounded-lg bg-blue-400">Generate pictures</button>
        </form>
    </div>
</template>

<script>
    export default {
        name: "ImageCard",
        props: ["src"]
    }
</script>