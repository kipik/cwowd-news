<template>
  <div class="base-100 min-h-screen">

    <Header />

    <main>
      <HeroSection />
      <FeaturedArticles :featuredArticles="myArticles" />
      <PromotedGames />
      <DiscussionsForum />
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
];

</script>
