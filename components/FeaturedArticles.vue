<!-- eslint-disable vue/first-attribute-linebreak -->
<template>
    <section class="base-100 py-12">
        <div class="container mx-auto px-4">
            <div class="flex items-center justify-between mb-4">
                <h2 class="text-2xl font-bold text-gray-400">Articles à la une</h2>
                <a href="#" class="text-blue-500">Tous les articles →</a>
            </div>
            <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
                <article v-for="article in featuredArticles" :key="article.id"
                    class="base-200 rounded-lg shadow-md p-4 transition-transform hover:scale-105 flex flex-col">
                    <nuxt-img :src="article.imageUrl" :alt="article.imageAlt"
                        class="mx-auto mb-2 h-64 w-full object-cover rounded-md lazy" />
                    <h3 class="text-lg text-gray-700 font-semibold">{{ article.title }}</h3>
                    <p class="text-xs text-gray-500 flex-grow">{{ article.description }}</p>
                    <div class="flex items-center mt-2 whitespace-nowrap">
                        <nuxt-img :src="article.authorAvatarUrl" :alt="article.author"
                            class="rounded-full w-8 h-8 mr-2" />
                        <div class="flex-1 flex items-end">
                            <p class="text-xs text-gray-500">{{ article.author }}</p>
                        </div>
                    </div>
                </article>
            </div>
            <p v-if="!featuredArticles.length" class="text-gray-500 text-center py-4">
                Aucun article à la une pour le moment.
            </p>
        </div>
    </section>
</template>

<script setup lang="ts">
import { NuxtImg } from '#components'

interface Article {
    id: string;
    title: string;
    description: string;
    imageUrl: string;
    imageAlt: string;
    author: string;
    authorAvatarUrl: string;
}

defineProps({
    featuredArticles: {
        type: Array as PropType<Article[]>,
        required: true,
    },
});
</script>