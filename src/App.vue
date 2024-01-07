<template>
    <body class="bg-gray-100 h-screen">
        <main class="w-full h-full flex justify-center items-center">
            <ImageCard />
        </main>
    </body>
</template>

<script>
import ImageCard from "./components/ImageCard/ImageCard.vue"

export default {
    name: 'App',
    components: {
        ImageCard
    },
    metaInfo() {
        return {
            title: 'CatPics',
            meta: [
                {
                    name: 'description',
                    content: 'Explore a collection of adorable cat images. Find the perfect photo for you!',
                },
                {
                    property: 'og:title',
                    content: 'CatPics',
                },
                {
                    property: 'og:description',
                    content: 'Explore a collection of adorable cat images. Find the perfect photo for you!',
                },
                {
                    property: 'og:image',
                    content: 'https://media.discordapp.net/attachments/1187766275007594576/1193657240801001573/c8e.jpg?ex=65ad82ef&is=659b0def&hm=4c298c09a22cd34084769d8229d5089f4a805014bed1ae520c7126ad3d071ed8&=&format=webp&width=623&height=467',
                },
                {
                    property: 'og:url',
                    content: 'https://cat-pics-one.vercel.app/',
                },
            ],
        };
    },
};

</script>