<template>
    <section class="base-300 py-12">
        <div class="container mx-auto px-4">
            <h2 class="text-2xl font-bold text-gray-400 mb-8">On en discute</h2>
            <div class="flex flex-col md:flex-row items-center justify-between mb-6 gap-4">
                <div class="flex justify-center w-full md:w-1/2">
                    <input type="text" placeholder="Rechercher une discussion..."
                        class="w-full px-4 py-2 rounded-full border border-gray-300 focus:ring-2 focus:ring-blue-500 text-black" />
                </div>
                <div class="flex items-center gap-4 w-full md:w-1/2 justify-center">
                    <span class="text-gray-500 text-sm">Filtrer par :</span>
                    <select
                        class="px-3 py-1 rounded-full border border-gray-300 focus:ring-2 focus:ring-blue-500 text-black text-sm">
                        <option value="date">Date</option>
                        <option value="popularite">Popularité</option>
                        <option value="categorie">Catégorie</option>
                    </select>
                </div>
            </div>
            <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
                <div>
                    <div class="flex items-center justify-between mb-4">
                        <h3 class="text-xl font-semibold text-gray-300">Sujets bouillants</h3>
                        <a href="#" class="text-blue-500 text-sm">
                            Voir plus <span aria-hidden="true">→</span>
                        </a>
                    </div>

                    <div class="space-y-4">
                        <article v-for="hotTopic in hotTopics.slice(0, 5)" :key="hotTopic.id"
                            class="base-100 rounded-lg shadow-md transition-shadow duration-200 hover:shadow-lg border border-gray-200">
                            <div class="p-3">
                                <div class="flex items-start">
                                    <NuxtLink :to="`/user/${hotTopic.author}`" class="mr-4 flex-shrink-0">
                                        <NuxtImg :src="hotTopic.avatarUrl" :alt="hotTopic.author"
                                            class="rounded-full w-12 h-12" />
                                    </NuxtLink>
                                    <div>
                                        <h4
                                            class="text-sm font-semibold text-gray-800 hover:text-blue-600 transition-colors">
                                            <NuxtLink :to="`/discussion/${hotTopic.id}`">
                                                {{ hotTopic.title }}
                                            </NuxtLink>
                                        </h4>
                                        <div class="flex flex-wrap items-center gap-2 mt-2 text-sm text-gray-500">
                                            <span class="font-semibold">{{ hotTopic.replies }} réponses</span>
                                            <span class="mx-0.5">•</span>
                                            <span>{{ hotTopic.views }} vues</span>
                                            <span class="mx-0.5">•</span>
                                            <span>{{ hotTopic.likes }}
                                                <Icon name="mdi:heart-multiple" size="16" class="inline-block ml-1" />
                                            </span>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </article>
                    </div>
                </div>
                <div>
                    <div class="flex items-center justify-between mb-4">
                        <h3 class="text-xl font-semibold text-gray-300">Les plus récentes</h3>
                        <a href="#" class="text-blue-500 text-sm">
                            Voir plus <span aria-hidden="true">→</span>
                        </a>
                    </div>
                    <div class="space-y-4">
                        <article v-for="recentTopic in recentTopics.slice(0, 5)" :key="recentTopic.id"
                            class="base-100 rounded-lg shadow-md transition-shadow duration-200 hover:shadow-lg border border-gray-200">
                            <div class="p-3">
                                <div class="flex items-start">
                                    <NuxtLink :to="`/user/${recentTopic.author}`" class="mr-4 flex-shrink-0">
                                        <NuxtImg :src="recentTopic.avatarUrl" :alt="recentTopic.author"
                                            class="rounded-full w-12 h-12" />
                                    </NuxtLink>
                                    <div>
                                        <h4
                                            class="text-sm font-semibold text-gray-800 hover:text-blue-600 transition-colors">
                                            <NuxtLink :to="`/discussion/${recentTopic.id}`">
                                                {{ recentTopic.title }}
                                            </NuxtLink>
                                        </h4>
                                        <div class="flex flex-wrap items-center gap-2 mt-2 text-sm text-gray-500">
                                            <span>Dernier message par </span>
                                            <NuxtLink :to="`/user/${recentTopic.author}`"
                                                class="text-blue-500 hover:underline">
                                                {{ recentTopic.author }}
                                            </NuxtLink>
                                            <span> {{ recentTopic.date }}</span>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </article>
                    </div>
                </div>
            </div>
            <div class="mt-8 text-center">
                <NuxtLink href="#" class="text-blue-500 font-medium hover:underline">
                    Voir toutes les discussions →
                </NuxtLink>
            </div>
        </div>
    </section>
</template>

<script setup lang="ts">
import { NuxtImg } from '#components'

interface Topic {
    id: string;
    title: string;
    author: string;
    avatarUrl: string;
    replies?: number;
    date: string;
    views?: number;
    likes?: number;
}

const hotTopics: Topic[] = [
    {
        id: "1",
        title: "Pour papoter des jeux Games Workshop",
        author: "FantomeZibin",
        avatarUrl: "https://avatar.iran.liara.run/public",
        replies: 183,
        date: "il y a 2 min",
        views: 1200,
        likes: 56
    },
    {
        id: "2",
        title: "Monolith - Le Flood",
        author: "Guylou",
        avatarUrl: "https://avatar.iran.liara.run/public",
        replies: 56,
        date: "il y a 5 min",
        views: 850,
        likes: 34
    },
    {
        id: "3",
        title: "Votre coup de coeur de la semaine ? Du 8 au 14 mars 2025",
        author: "Jean-Phi",
        avatarUrl: "https://avatar.iran.liara.run/public",
        replies: 12,
        date: "il y a 8 j",
        views: 210,
        likes: 12
    },
    {
        id: "4",
        title: "Des figurines Blood Bowl à gogo",
        author: "Xavier",
        avatarUrl: "https://avatar.iran.liara.run/public",
        replies: 200,
        date: "il y a 1h",
        views: 1500,
        likes: 78
    },
    {
        id: "5",
        title: "Le JDR Star Wars est-il bien ?",
        author: "Marie",
        avatarUrl: "https://avatar.iran.liara.run/public",
        replies: 95,
        date: "il y a 3h",
        views: 650,
        likes: 23
    }
];

const recentTopics: Topic[] = [
    {
        id: "4",
        title: "Chronicles of Katura - Le jeu de rôle collaboratif épique",
        author: "Melissa",
        avatarUrl: "https://avatar.iran.liara.run/public",
        replies: 28,
        date: "il y a 15 s",
    },
    {
        id: "5",
        title: "Conseils pour des jeux de société pour enfants de 6 ans",
        author: "Nicolas",
        avatarUrl: "https://avatar.iran.liara.run/public",
        replies: 33,
        date: "il y a 1 min",
    },
    {
        id: "6",
        title: "Nouvelle extension pour Terraforming Mars",
        author: "Sophie",
        avatarUrl: "https://avatar.iran.liara.run/public",
        replies: 45,
        date: "il y a 3 min",
    },
    {
        id: "7",
        title: "Peindre ses figurines pour les nuls",
        author: "Antoine",
        avatarUrl: "https://avatar.iran.liara.run/public",
        replies: 62,
        date: "il y a 4 min"
    },
    {
        id: "8",
        title: "Quelqu'un a testé le nouveau Marvel United ?",
        author: "Camille",
        avatarUrl: "https://avatar.iran.liara.run/public",
        replies: 88,
        date: "il y a 6 min",
    }
];

/* const heartIcon = `<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-heart"><path d="M19 14c1.49-1.46 3-3.21 3-5.5A5.5 5.5 0 0 0 16.5 3c-1.76 0-3 1.35-3 2.66-1.15-1.13-3-2.66-3-2.66A5.5 5.5 0 0 0 2 8.5c0 2.3 1.51 4.04 3 5.5a6.51 6.51 0 0 0 16 0Z"/></svg>`;
*/
</script>

*/
voici quelques suggestions pour améliorer la section "On en discute" :

Structure et contenu :

Pagination : ajoutez une pagination pour faciliter la navigation.


Interface utilisateur :

Ajouter des indicateurs visuels : Utilisez des icônes ou des couleurs pour indiquer le statut d'une discussion (par
exemple, si elle est fermée, si elle contient de nouvelles réponses, etc.).

Fonctionnalités :

Intégration avec d'autres sections : Intégrez la section "On en discute" avec d'autres sections du site, comme les
articles ou les publications, pour encourager la participation et les échanges.
