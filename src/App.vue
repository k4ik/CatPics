<template>
    <body class="bg-gray-100 h-screen">
        <main class="w-full h-full flex justify-center items-center">
            <ImageCard/>
        </main>
    </body>
</template>

<script>
    import ImageCard from "./components/ImageCard/ImageCard.vue"

    export default {
        name: "App",
        components: {
            ImageCard
        }
    }
</script>