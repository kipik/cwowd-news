<template>
    <div class="space-y-4">
        <div class="flex items-center justify-between mb-4">
            <h3 class="text-xl font-semibold text-gray-300">{{ columnTitle }}</h3>
            <a :href="viewMoreUrl" v-if="viewMoreUrl" class="text-blue-500 text-sm">
                Voir plus <span aria-hidden="true">→</span>
            </a>
            <a href="#" v-else class="text-blue-500 text-sm">
                Voir plus <span aria-hidden="true">→</span>
            </a>

        </div>
        <div class="space-y-4">
            <article v-for="topic in topics" :key="topic.id"
                class="base-100 rounded-lg shadow-md transition-shadow duration-200 hover:shadow-lg border border-gray-200">
                <div class="p-3">
                    <div class="flex items-start">
                        <NuxtLink :to="`/discussion/${topic.id}`" class="mr-4 flex-shrink-0">
                            <NuxtImg :src="topic.avatarUrl" :alt="topic.author" class="rounded-full w-12 h-12" />
                        </NuxtLink>
                        <div>
                            <h4 class="text-sm font-semibold text-gray-800 hover:text-blue-600 transition-colors">
                                <NuxtLink :to="`/discussion/${topic.id}`">
                                    {{ topic.title }}
                                </NuxtLink>
                            </h4>
                            <div class="flex flex-wrap items-center gap-2 mt-2 text-sm text-gray-500">
                                <template v-if="displayStyle === 'hot'">
                                    <span class="font-semibold">{{ topic.replies }} réponses</span>
                                    <span class="mx-0.5">•</span>
                                    <span>{{ topic.views }} vues</span>
                                    <span class="mx-0.5">•</span>
                                    <span>{{ topic.likes }}
                                        <Icon name="mdi-heart-multiple" size="16" class="inline-block ml-1" />
                                    </span>
                                </template>
                                <template v-else-if="displayStyle === 'recent'">
                                    <span>Dernier message par </span>
                                    <NuxtLink :to="`/user/${topic.author}`" class="text-blue-500 hover:underline">
                                        {{ topic.author }}
                                    </NuxtLink>
                                    <span> {{ topic.date }}</span>
                                </template>
                                <template v-else>
                                    <span>{{ topic.author }}</span>
                                    <span class="mx-0.5">•</span>
                                    <span>{{ topic.date }}</span>
                                </template>
                            </div>

                        </div>
                    </div>
                </div>
            </article>
        </div>
    </div>
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

const props = defineProps({
    title: {
        type: String,
        default: "On en discute",
    },
    columnTitle: {
        type: String,
        required: true,
    },
    topics: {
        type: Array<Topic>,
        required: true,
    },
    displayStyle: {
        type: String,
        validator: (value: string) => ['hot', 'recent', 'basic'].includes(value),
        default: 'basic'
    },
    viewMoreUrl: {
        type: String,
        default: undefined
    }
});

/* Quelques suggestions pour améliorer la section "On en discute" :

Structure et contenu :
Pagination : ajoutez une pagination pour faciliter la navigation.

Interface utilisateur :
Ajouter des indicateurs visuels : Utilisez des icônes ou des couleurs pour indiquer le statut d'une discussion (par
exemple, si elle est fermée, si elle contient de nouvelles réponses, etc.).

Fonctionnalités :
Intégration avec d'autres sections : Intégrez la section "On en discute" avec d'autres sections du site, comme les
articles ou les publications, pour encourager la participation et les échanges.

Gérer l'affichage des icônes : L'utilisation de Icon pour l'icône de cœur est bien, mais assurez-vous que la
bibliothèque d'icônes est correctement configurée et que l'icône est toujours disponible. Si ce n'est pas le cas,
prévoyez une alternative ou un message d'erreur clair.

*/

</script>
