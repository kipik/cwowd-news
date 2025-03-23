<template>
    <section class="base-300 py-12">
        <div class="container mx-auto px-4">

            <h2 class="text-2xl font-bold text-gray-400 mb-8">À la une</h2>

            <div v-if="featuredArticles.length" class="relative w-full">

                <Carousel :opts="{ align: 'start', loop: true }">
                    <CarouselContent class="-ml-6">
                        <CarouselItem v-for="article in featuredArticles" :key="article.id"
                            class="pl-4 md:basis-1/2 lg:basis-1/3 transition-opacity duration-500"
                            :style="{ opacity: isCurrent(article.id) ? 1 : 0.7 }">
                            <article
                                class="rounded-lg shadow-md transition-shadow duration-200 hover:shadow-lg border border-gray-200 flex flex-col h-full">
                                <NuxtLink :to="`/article/${article.id}`">
                                    <NuxtImg :src="article.imageUrl" :alt="article.imageAlt"
                                        class="rounded-t-lg w-full h-80 object-cover" />
                                </NuxtLink>
                                <div class="p-6 flex-grow flex flex-col">
                                    <h3
                                        class="text-lg font-semibold text-gray-800 hover:text-blue-600 transition-colors">
                                        <NuxtLink :to="`/article/${article.id}`">
                                            {{ article.title }}
                                        </NuxtLink>
                                    </h3>
                                    <p class="text-gray-600 mt-2 mb-1 line-clamp-3">
                                        {{ article.description }}
                                    </p>
                                </div>
                                <div class="flex items-center justify-end mt-auto p-1  border-gray-200">
                                    <NuxtImg :src="article.authorAvatarUrl" :alt="article.author"
                                        class="rounded-full w-8 h-8 mr-2" />
                                    <p class="text-xs text-gray-500 ml-2 mr-4">Par {{ article.author }}</p>
                                </div>
                            </article>
                        </CarouselItem>
                    </CarouselContent>
                    <CarouselPrevious />
                    <CarouselNext />
                </Carousel>

            </div>
            <p v-if="!featuredArticles.length" class="text-gray-500 text-center py-4">
                Aucun article à la une pour le moment.
            </p>
        </div>
    </section>
</template>

<script setup lang="ts">
import { NuxtImg } from "#components";
import {
    Carousel,
    CarouselContent,
    CarouselItem,
    CarouselPrevious,
    CarouselNext,
} from "@/components/ui/carousel";
import { ref, onMounted } from "vue";

interface Article {
    id: string;
    title: string;
    description: string;
    imageUrl: string;
    imageAlt: string;
    author: string;
    authorAvatarUrl: string;
}

const props = defineProps({
    featuredArticles: {
        type: Array as PropType<Article[]>,
        required: true,
    },
});

const currentArticleId = ref<string | null>(null);

const isCurrent = (id: string) => {
    return currentArticleId.value === id;
};

onMounted(() => {
    if (props.featuredArticles.length > 0) {
        currentArticleId.value = props.featuredArticles[0].id;
    }
});
</script>


/**
Améliorer la gestion des images
Utilisez des balises <img> avec des attributs srcset et sizes pour optimiser le chargement des images sur différents
appareils.
Pensez également à utiliser un service d'optimisation d'image pour réduire la taille des fichiers image.

Gérer les erreurs de chargement d'image
Ajoutez une gestion des erreurs pour les cas où les images ne peuvent pas être chargées
(par exemple, en affichant une image de remplacement ou un message d'erreur).


Améliorer la navigation
Vous pourriez améliorer la navigation du carrousel en ajoutant des indicateurs de page (points ou barres)
pour indiquer le nombre total d'articles et la position actuelle de l'utilisateur.
Vous pourriez également ajouter des flèches de navigation plus visibles et personnalisables.

Optimiser les images :
Pour améliorer les performances du carrousel, il est important d'optimiser les images.
Vous pourriez utiliser des images compressées et redimensionnées pour chaque appareil.
Vous pourriez également utiliser le chargement paresseux pour charger les images uniquement lorsqu'elles sont visibles à
l'écran.

Améliorer l'accessibilité
Pour rendre le carrousel accessible aux utilisateurs handicapés, vous pourriez ajouter des attributs ARIA appropriés.
Par exemple, vous pourriez ajouter des attributs aria-label aux boutons de navigation et des attributs aria-hidden aux
éléments non interactifs.

Personnaliser l'apparence : Vous pourriez permettre aux utilisateurs de personnaliser l'apparence du carrousel en
ajoutant des options de style.
Par exemple, vous pourriez permettre aux utilisateurs de changer la couleur de fond, la couleur du texte, la taille des
images et la police.
**/
