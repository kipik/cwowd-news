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
              class="w-full md:w-1/2" :viewMoreUrl="hotTopicsViewMoreUrl" />
            <DiscussionsForum columnTitle="Dernières discussions" :topics="recentTopics" displayStyle="recent"
              class="w-full md:w-1/2" :viewMoreUrl="recentTopicsViewMoreUrl" />
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
  {
    id: '4',
    title: 'Exploration des Ruines de Zephyria',
    description:
      'Plongez dans une aventure épique avec ce jeu de société coopératif où les joueurs explorent les ruines antiques de Zephyria. Affrontez des énigmes et des créatures mystérieuses pour découvrir les secrets oubliés.',
    imageUrl: 'https://i.postimg.cc/CMGwfpPh/0cc7d2c4-1ba6-49e9-8cce-dee64e5d026c-jpg.webp',
    imageAlt: 'Ruines de Zephyria',
    author: 'Alice',
    authorAvatarUrl: 'https://avatar.iran.liara.run/public/alice',
  },
  {
    id: '5',
    title: 'Le Mystère des Îles Flottantes',
    description:
      'Dans ce jeu de stratégie, les joueurs doivent naviguer entre des îles flottantes pour résoudre un mystère ancien. Collectez des ressources, construisez des alliances et découvrez les secrets cachés dans les nuages.',
    imageUrl: 'https://i.postimg.cc/cCZXkNGr/1d2baf89-5e68-4305-b67c-d339ed9bb9d5.webp',
    imageAlt: 'Îles Flottantes',
    author: 'Bob',
    authorAvatarUrl: 'https://avatar.iran.liara.run/public/bob',
  },
  {
    id: '6',
    title: 'La Révolte des Automates',
    description:
      'Dans un futur dystopique, les automates se rebellent contre leurs créateurs. Les joueurs doivent choisir leur camp et lutter pour le contrôle de la ville dans ce jeu de stratégie intense.',
    imageUrl: 'https://i.postimg.cc/8CKFq9R6/Lord_of_the_Rings_The_Confrontation_–_Ghost_Galaxy.png',
    imageAlt: 'Révolte des Automates',
    author: 'Charlie',
    authorAvatarUrl: 'https://avatar.iran.liara.run/public/charlie',
  },
  {
    id: '7',
    title: 'Le Jardin Enchanté',
    description:
      'Un jeu familial où les joueurs doivent cultiver et entretenir un jardin magique. Plantez des fleurs, attirez des créatures féeriques et faites pousser le plus beau jardin pour gagner.',
    imageUrl: 'https://i.postimg.cc/FFC5R49n/Action-Packed-Double-Feature.png',
    imageAlt: 'Jardin Enchanté',
    author: 'Diana',
    authorAvatarUrl: 'https://avatar.iran.liara.run/public/diana',
  },
  {
    id: '8',
    title: 'Les Chroniques de la Guilde des Voleurs',
    description:
      'Devenez un maître voleur et accomplissez des missions périlleuses dans ce jeu d’aventure. Évitez les gardes, déjouez les pièges et amassez le plus grand butin possible.',
    imageUrl: 'https://i.postimg.cc/NMngrckV/Bullet-Cubed-New-Expansions-Storage-Box.webp',
    imageAlt: 'Guilde des Voleurs',
    author: 'Eve',
    authorAvatarUrl: 'https://avatar.iran.liara.run/public/eve',
  },
  {
    id: '9',
    title: 'L’Expédition Polaire',
    description:
      'Partez en expédition dans les régions polaires pour découvrir des trésors cachés et survivre aux conditions extrêmes. Ce jeu de survie mettra à l’épreuve vos compétences et votre esprit d’équipe.',
    imageUrl: 'https://i.postimg.cc/T1D36FQc/cf4f887d75585ea47140c4d15ad2427e756a0bf8-2-690x350.jpg',
    imageAlt: 'Expédition Polaire',
    author: 'Frank',
    authorAvatarUrl: 'https://avatar.iran.liara.run/public/frank',
  },
  {
    id: '10',
    title: 'Le Royaume des Dragons',
    description:
      'Dans ce jeu de stratégie, les joueurs incarnent des seigneurs dragons luttant pour le contrôle d’un royaume mythique. Utilisez vos pouvoirs draconiques pour conquérir des territoires et vaincre vos ennemis.',
    imageUrl: 'https://i.postimg.cc/fbXVg99d/Yomi_2.webp',
    imageAlt: 'Royaume des Dragons',
    author: 'Grace',
    authorAvatarUrl: 'https://avatar.iran.liara.run/public/grace',
  }
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

const hotTopicsViewMoreUrl = "https://forum.cwowd.com/top";
const recentTopicsViewMoreUrl = "https://forum.cwowd.com/latest";

/** 
 
 * Simplifier la structure des données
 Si les données hotTopics et recentTopics proviennent d'une source externe (API, base de données), 
 envisagez de normaliser la structure des données pour faciliter leur gestion et leur mise à jour.

 * Ajouter des commentaires
 Bien que le code soit assez clair, l'ajout de commentaires plus détaillés, 
 en particulier pour expliquer la logique métier ou les choix architecturaux, 
 améliorerait la maintenabilité du code.

 * Accessibilité
 Assurez-vous que votre code est accessible aux personnes handicapées en utilisant des balises HTML sémantiques, 
 en fournissant un contraste de couleurs suffisant et en ajoutant des attributs alt descriptifs aux images.

 * Performances
 Utilisez un outil d'analyse de performances pour identifier les goulots d'étranglement potentiels et optimiser votre code en conséquence. 
 Par exemple, vous pouvez utiliser la mise en cache, la compression et la minification pour améliorer les temps de chargement des pages.

 * Tests
 Écrivez des tests unitaires et des tests d'intégration pour vous assurer que votre code fonctionne comme prévu et qu'il est facile à maintenir et à faire évoluer.

 Uniformiser les props avec les termes de Discourse (latest etc.)
*/
</script>
