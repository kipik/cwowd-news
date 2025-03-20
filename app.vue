<template>
  <div class="base-100 min-h-screen">

    <Header />

    <main>
      <HeroSection />
      <FeaturedArticles :featured-articles="myArticles" />
      <PromotedGames />
      <section class="base-300 py-12">
        <div class="container mx-auto px-4">
          <h2 class="text-2xl font-bold text-gray-400 mb-8">On en discute</h2>
          <div class="flex flex-col md:flex-row items-center justify-between mb-6 gap-4">
            <div class="flex justify-center w-full ">
              <input type="text" placeholder="Rechercher une discussion..."
                class="w-full px-4 py-2 rounded-full border border-gray-300 focus:ring-2 focus:ring-blue-500 text-black" />
            </div>
            <div class="flex items-center gap-4 w-full  justify-center">
              <span class="text-gray-500 text-sm">Filtrer par :</span>
              <select
                class="px-3 py-1 rounded-full border border-gray-300 focus:ring-2 focus:ring-blue-500 text-black text-sm">
                <option value="date">Date</option>
                <option value="popularite">Popularité</option>
                <option value="categorie">Catégorie</option>
              </select>
            </div>
          </div>
          <div class="flex flex-col md:flex-row gap-8">
            <DiscussionsForum columnTitle="Sujets brûlants" :topics="hotTopics" displayStyle="hot"
              class="w-full md:w-1/2" />
            <DiscussionsForum columnTitle="Dernières discussions" :topics="recentTopics" displayStyle="recent"
              class="w-full md:w-1/2" />
          </div>

          <div class="mt-8 text-center">
            <a href="#" class="text-blue-500 font-medium hover:underline">
              Voir toutes les discussions →
            </a>
          </div>
        </div>
      </section>
      <ParolesDeJoueurs />
    </main>

    <FooterGlobal />

  </div>
</template>

<script setup lang="ts">
import Header from '@/components/Header.vue';
import HeroSection from '@/components/HeroSection.vue';
import FeaturedArticles from '@/components/FeaturedArticles.vue';
import PromotedGames from '@/components/PromotedGames.vue';
import DiscussionsForum from '@/components/DiscussionsForum.vue';
import ParolesDeJoueurs from '@/components/ParolesDeJoueurs.vue';
import FooterGlobal from './components/FooterGlobal.vue';

const myArticles = [
  {
    id: '1',
    title: 'Ozob: A Cyberpunk Board Game',
    description:
      'Ozob plonge les joueurs dans un univers cyberpunk sombre et dangereux, où ils incarnent des rebelles, hackers, déviants etc. luttant contre les mégacorporations (what else ?). Ludiquement, il s’agit d’un dungeon crawler, coopératif, ambiancé cyberpunk tendance bas-fonds glauques. Les amateurs s’en seront doutés au titre.',
    imageUrl: 'https://i.postimg.cc/DZ4Hfj7Q/OZOB-A-Cyberpunk-Boardgame-Nonsense-Creations.png',
    imageAlt: 'Ozob: A Cyberpunk Board Game',
    author: 'Thierry',
    authorAvatarUrl: 'https://avatar.iran.liara.run/public',
  },
  {
    id: '2',
    title: 'La nouvelle annonce sur GF : Qu’arz',
    description:
      'Aucune idée de ce dont il s’agit, c’est juste mon oeil qui fait des siennes, dès qu’il y a des images choupinesques, il papillonne…',
    imageUrl: 'https://i.postimg.cc/qvsxh8sN/34d534ff-47d5-4055-af9c-49f41e96e986.webp',
    imageAlt: 'Bientôt sur GF : Qu’arz',
    author: 'Leskiv27',
    authorAvatarUrl: 'https://avatar.iran.liara.run/public/boy',
  },
  {
    id: '3',
    title: 'Menu participatif et ludique de la semaine – Episode 1',
    description:
      'Découvrez les projets ludiques les plus excitants de la semaine dans notre menu participatif du 12 mars 2025 ! Bôken, Gudnak, Too Many Bones, et bien plus encore... Quel jeu allez-vous soutenir ?',
    imageUrl:
      '3-joueurs-joueuses-assis-autour-d-une-table--jouan.png',
    imageAlt: 'Les infos ludiques de la semaine',
    author: 'MathemW, Basara & Nsan',
    authorAvatarUrl: 'https://avatar.iran.liara.run/public/37',
  },
]

const hotTopics = [
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

const recentTopics = [
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

</script>
