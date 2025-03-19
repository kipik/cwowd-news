<template>
  <div class="base-100 min-h-screen">
    <!-- Header -->
    <header class="header bg-primary-content shadow">


      <div class="navbar bg-primary-content shadow-sm">
        <div class="navbar-start">
          <div class="dropdown">
            <div tabindex="0" role="button" class="btn btn-ghost lg:hidden">
              <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="none" viewBox="0 0 24 24"
                stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h8m-8 6h16" />
              </svg>
            </div>
            <ul tabindex="0"
              class="menu menu-sm dropdown-content bg-base-100 rounded-box z-1 mt-3 w-52 p-2 shadow navbar-list space-x-6">
              <li><a href="#" class="navbar-list-link">Accueil</a></li>
              <li><a href="#" class="navbar-list-link">Articles</a></li>
              <li><a href="#" class="navbar-list-link">Publications</a></li>
              <li><a href="#" class="navbar-list-link">Paroles</a></li>
              <li><a href="#" class="navbar-list-link">On en discute</a></li>
            </ul>
          </div>
          <a class="btn btn-ghost text-2xl font-bold">Cwowd.com</a>
        </div>
        <div class="navbar-center hidden lg:flex">
          <ul class="menu menu-horizontal px-1">
            <li><a href="#" class="navbar-list-link">Accueil</a></li>
            <li><a href="#" class="navbar-list-link">Articles</a></li>
            <li><a href="#" class="navbar-list-link">Publications</a></li>
            <li><a href="#" class="navbar-list-link">Paroles</a></li>
            <li><a href="#" class="navbar-list-link">On en discute</a></li>
          </ul>
        </div>
        <div class="navbar-end">
          <input type="text" placeholder="On cherche quoi?" class="px-2 py-1 rounded-md border border-gray-300">

          <button class="btn btn-ghost btn-circle">
            <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="none" viewBox="0 0 24 24"
              stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z" />
            </svg>
          </button>
          <button class="btn btn-ghost btn-circle">
            <div class="indicator">
              <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="none" viewBox="0 0 24 24"
                stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                  d="M15 17h5l-1.405-1.405A2.032 2.032 0 0118 14.158V11a6.002 6.002 0 00-4-5.659V5a2 2 0 10-4 0v.341C7.67 6.165 6 8.388 6 11v3.159c0 .538-.214 1.055-.595 1.436L4 17h5m6 0v1a3 3 0 11-6 0v-1m6 0H9" />
              </svg>
              <span class="badge badge-xs badge-primary indicator-item"></span>
            </div>
          </button>
        </div>
      </div>
    </header>

    <!-- Hero Section -->
    <section class="relative base-200 py-32">
      <img src="/assets/images/hero-section.jpg" alt="Hero Image" class="absolute inset-0 object-cover w-full h-full" />
      <div class="absolute inset-0 bg-black opacity-50"></div>
      <div class="container mx-auto px-4 relative z-10 text-center">
        <h1 class="text-5xl font-bold text-white mb-4">Bienvenue sur Cwowd</h1>
        <p class="text-xl text-gray-300 mb-8">Découvrez l'actualité ludique et participative</p>
        <div class="flex items-center justify-center space-x-4">
          <a href="#" class="btn btn-soft btn-primary px-6 py-3  font-semibold hover:bg-primary">Lire
            les
            articles</a>
          <a href="#"
            class="btn btn-active btn-primary border border-gray-300 text-white px-6 py-3 rounded-md font-semibold hover:bg-gray-700">Rejoindre
            le forum</a>
        </div>
        <p class="text-md text-gray-300 mb-8">Une communauté de joueurs unique avec qui partager votre passion, vos
          découvertes, tests, impressions et bons comme mauvais moments.</p>

      </div>
    </section>

    <!-- Articles à la une -->
    <section class="base-100 py-12">
      <div class="container mx-auto px-4">
        <div class="flex items-center justify-between mb-4">
          <h2 class="text-2xl font-bold">Articles à la une</h2>
          <a href="#" class="text-blue-500">Tous les articles →</a>
        </div>
        <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
          <div class="base-200 rounded-lg shadow-md p-4">
            <img src="https://i.postimg.cc/DZ4Hfj7Q/OZOB-A-Cyberpunk-Boardgame-Nonsense-Creations.png" alt="Article 1"
              class="mx-auto mb-2 h-64 w-full object-cover" />
            <h3 class="text-sm font-semibold">Ozob: A Cyberpunk Board Game</h3>
            <p class="text-xs text-gray-500">Ozob plonge les joueurs dans un univers cyberpunk sombre et dangereux, où
              ils incarnent des rebelles, hackers, déviants etc. luttant contre les mégacorporations (what else ?).
              Ludiquement, il s’agit d’un dungeon crawler, coopératif, ambiancé cyberpunk tendance bas-fonds glauques.
              Les amateurs s’en seront doutés au titre. </p>
            <div class="flex items-center mt-2 whitespace-nowrap">
              <img src="https://avatar.iran.liara.run/public" alt="Thierry" class="rounded-full w-8 h-8 mr-2" />
              <div>
                <p class="text-xs text-gray-500">Author 1</p>
              </div>
            </div>
          </div>
          <div class="base-200 rounded-lg shadow-md p-4">
            <img src="https://i.postimg.cc/qvsxh8sN/34d534ff-47d5-4055-af9c-49f41e96e986.webp"
              alt="Bientôt sur GF : Qu’arz" class="mx-auto mb-2 h-64 w-full object-cover" />
            <h3 class="text-sm font-semibold">La nouvelle annonce sur GF : Qu’arz</h3>
            <p class="text-xs text-gray-500">Aucune idée de ce dont il s’agit, c’est juste mon oeil qui fait des
              siennes, dès qu’il y a des images choupinesques, il papillonne…

            </p>
            <div class="flex items-center mt-2 whitespace-nowrap">
              <img src="https://avatar.iran.liara.run/public/boy" alt="Leskiv27" class="rounded-full w-8 h-8 mr-2" />
              <div>
                <p class="text-xs text-gray-500">Author 2</p>
              </div>
            </div>
          </div>
          <div class="base-200 rounded-lg shadow-md p-4">
            <img src="assets\images\3-joueurs-joueuses-assis-autour-d-une-table--jouan.png"
              alt="Les infos ludiques d ela semaine" class="mx-auto mb-2 h-64 w-full object-cover" />
            <h3 class="text-sm font-semibold">Menu participatif et ludique de la semaine – Episode 1</h3>
            <p class="text-xs text-gray-500">Découvrez les projets ludiques les plus excitants de la semaine dans
              notre
              menu participatif du 12 mars 2025 ! Bôken, Gudnak, Too Many Bones, et bien plus encore... Quel jeu
              allez-vous soutenir ?
            </p>
            <div class="flex items-center mt-2 whitespace-nowrap">
              <img src="https://avatar.iran.liara.run/public/37" alt="MathemW, Basara & Nsan"
                class="rounded-full w-8 h-8 mr-2" />
              <div>
                <p class="text-xs text-gray-500">Author 3</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Games in promotion -->
    <section class="base-100 py-12">
      <div class="container mx-auto px-4">
        <div class="flex items-center justify-between mb-4">
          <h2 class="text-2xl font-bold">Jeux en promotion</h2>
          <a href="#" class="text-blue-500">Voir toutes les offres →</a>
        </div>
        <div class="grid grid-cols-1 md:grid-cols-5 gap-4">
          <div class="base-200 rounded-lg shadow-md p-4">
            <img src="assets\images\Azul - English second edition, 2018.png" alt="Azul" class="mx-auto mb-2">
            <h3 class="text-sm font-semibold">Azul - Plan B Games</h3>
            <p class="text-gray-500">30,99 €</p>
            <p class="text-xs text-gray-500">Amazon</p>
          </div>
          <div class="base-200 rounded-lg shadow-md p-4">
            <img src="assets\images\Edge Quest.jpg" alt="7 Wonders" class="mx-auto mb-2">
            <h3 class="text-sm font-semibold">7 Wonders - Seconde Edition</h3>
            <p class="text-gray-500">45,50 €</p>
            <p class="text-xs text-gray-500">Philbert</p>
          </div>
          <div class="base-200 rounded-lg shadow-md p-4">
            <img src="assets\images\Formaggio.jpg" alt="Pandemic" class="mx-auto mb-2">
            <h3 class="text-sm font-semibold">Pandemic - Le Jeu de Base</h3>
            <p class="text-gray-500">29,90 €</p>
            <p class="text-xs text-gray-500">Amazon</p>
          </div>
          <div class="base-200 rounded-lg shadow-md p-4">
            <img src="assets\images\sail.jpg" alt="Carcassonne" class="mx-auto mb-2">
            <h3 class="text-sm font-semibold">Carcassonne - Edition 2021</h3>
            <p class="text-gray-500">29,00 €</p>
            <p class="text-xs text-gray-500">Esprit Jeu</p>
          </div>
          <div class="base-200 rounded-lg shadow-md p-4">
            <img src="assets\images\Unbreakable.jpg" alt="Catan" class="mx-auto mb-2">
            <h3 class="text-sm font-semibold">Catan - Big Box</h3>
            <p class="text-gray-500">70,00 €</p>
            <p class="text-xs text-gray-500">Philbert</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Forum Discussions -->
    <section class="base-300 py-12">
      <div class="container mx-auto px-4">
        <div class="flex items-center justify-between mb-4">
          <h2 class="text-2xl font-bold">Discussions récentes du forum</h2>
          <a href="#" class="text-blue-500">Voir toutes les discussions →</a>
        </div>
        <div class="base-100 rounded-lg shadow-md p-4">
          <ul>
            <li class="py-2 border-b border-gray-200">
              <div class="flex items-center">
                <img src="https://via.placeholder.com/32" alt="Avatar" class="rounded-full w-8 h-8 mr-2">
                <div>
                  <p class="text-sm font-semibold">Pour papoter des jeux Games Workshop</p>
                  <p class="text-xs text-gray-500">FantomeZibin - 183 réponses - il y a 2 min</p>
                </div>
              </div>
            </li>
            <li class="py-2 border-b border-gray-200">
              <div class="flex items-center">
                <img src="https://via.placeholder.com/32" alt="Avatar" class="rounded-full w-8 h-8 mr-2">
                <div>
                  <p class="text-sm font-semibold">Monolith - Le Flood</p>
                  <p class="text-xs text-gray-500">Guylou - 56 réponses - il y a 5 min</p>
                </div>
              </div>
            </li>
            <li class="py-2 border-b border-gray-200">
              <div class="flex items-center">
                <img src="https://via.placeholder.com/32" alt="Avatar" class="rounded-full w-8 h-8 mr-2">
                <div>
                  <p class="text-sm font-semibold">Votre coup de coeur de la semaine ? Du 8 au 14 mars 2025</p>
                  <p class="text-xs text-gray-500">Jean-Phi - 12 réponses - il y a 8 j</p>
                </div>
              </div>
            </li>
            <li class="py-2 border-b border-gray-200">
              <div class="flex items-center">
                <img src="https://via.placeholder.com/32" alt="Avatar" class="rounded-full w-8 h-8 mr-2">
                <div>
                  <p class="text-sm font-semibold">Chronicles of Katura - Le jeu de rôle collaboratif épique</p>
                  <p class="text-xs text-gray-500">Melissa - 28 réponses - il y a 3h</p>
                </div>
              </div>
            </li>
            <li class="py-2">
              <div class="flex items-center">
                <img src="https://via.placeholder.com/32" alt="Avatar" class="rounded-full w-8 h-8 mr-2">
                <div>
                  <p class="text-sm font-semibold">Conseils pour des jeux de société pour enfants de 6 ans</p>
                  <p class="text-xs text-gray-500">Nicolas - 33 réponses - il y a 2 j</p>
                </div>
              </div>
            </li>
          </ul>
        </div>
      </div>
    </section>

    <!-- Recent Publications -->
    <section class="base-100 py-12">
      <div class="container mx-auto px-4">
        <div class="flex items-center justify-between mb-4">
          <h2 class="text-2xl font-bold">Publications récentes</h2>
          <a href="#" class="text-blue-500">Toutes les publications →</a>
        </div>
        <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
          <div class="base-200 rounded-lg shadow-md p-4">
            <img src="https://via.placeholder.com/200" alt="Stella" class="mx-auto mb-2">
            <h3 class="text-sm font-semibold">Stella: Dixit Universe - Premières impressions</h3>
            <p class="text-xs text-gray-500">Ce nouveau jeu dans l'univers Dixit apporte une dimension stratégique
              inédite tout en...</p>
            <div class="flex items-center mt-2">
              <img src="https://via.placeholder.com/32" alt="Lucas Dubois" class="rounded-full w-8 h-8 mr-2">
              <div>
                <p class="text-xs text-gray-500">Lucas Dubois</p>
              </div>
            </div>
          </div>
          <div class="base-200 rounded-lg shadow-md p-4">
            <img src="https://via.placeholder.com/200" alt="Zombicide" class="mx-auto mb-2">
            <h3 class="text-sm font-semibold">Zombicide 2.0 - Un reboot nécessaire ?</h3>
            <p class="text-xs text-gray-500">CMON revisite son best-seller en simplifiant les règles. Un bon point
              pour
              les nouveaux...</p>
            <div class="flex items-center mt-2">
              <img src="https://via.placeholder.com/32" alt="Marie Lefèvre" class="rounded-full w-8 h-8 mr-2">
              <div>
                <p class="text-xs text-gray-500">Marie Lefèvre</p>
              </div>
            </div>
          </div>
          <div class="base-200 rounded-lg shadow-md p-4">
            <img src="https://via.placeholder.com/200" alt="Weather Machine" class="mx-auto mb-2">
            <h3 class="text-sm font-semibold">Weather Machine - Enfin sur nos tables !</h3>
            <p class="text-xs text-gray-500">Après des mois d'attente suite au Kickstarter, Weather Machine de
              Vital...
            </p>
            <div class="flex items-center mt-2">
              <img src="https://via.placeholder.com/32" alt="Alexandre Petit" class="rounded-full w-8 h-8 mr-2">
              <div>
                <p class="text-xs text-gray-500">Alexandre Petit</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Quotes/Testimonials -->
    <section class="base-300 py-12">
      <div class="container mx-auto px-4">
        <h2 class="text-2xl font-bold mb-4">Ils ont dit...</h2>
        <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
          <div class="base-100 rounded-lg shadow-md p-4">
            <p class="text-gray-600">"Après 5 parties, je peux affirmer que c'est mon jeu préféré de 2024. Les
              mécaniques s'imbriquent parfaitement et chaque partie est différente."</p>
            <div class="flex items-center mt-2">
              <img src="https://via.placeholder.com/32" alt="Philippe" class="rounded-full w-8 h-8 mr-2">
              <div>
                <p class="text-sm font-semibold">Philippe</p>
                <p class="text-xs text-gray-500">A propos de Cascadia</p>
              </div>
            </div>
          </div>
          <div class="base-100 rounded-lg shadow-md p-4">
            <p class="text-gray-600">"Je suis généralement réticent avec les jeux coopératifs, mais celui-ci a réussi
              à
              me convaincre grâce à son système de communication limité qui..."</p>
            <div class="flex items-center mt-2">
              <img src="https://via.placeholder.com/32" alt="Sandrine" class="rounded-full w-8 h-8 mr-2">
              <div>
                <p class="text-sm font-semibold">Sandrine</p>
                <p class="text-xs text-gray-500">A propos de The Crew</p>
              </div>
            </div>
          </div>
          <div class="base-100 rounded-lg shadow-md p-4">
            <p class="text-gray-600">"Ce jeu ne paye pas de mine avec son petit format, mais quelle profondeur
              stratégique ! C'est devenu notre jeu de fin de soirée favori."</p>
            <div class="flex items-center mt-2">
              <img src="https://via.placeholder.com/32" alt="Mathieu" class="rounded-full w-8 h-8 mr-2">
              <div>
                <p class="text-sm font-semibold">Mathieu</p>
                <p class="text-xs text-gray-500">A propos de Mindbug</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Footer -->
    <footer class="neutral text-white py-8">
      <div class="container mx-auto px-4">
        <div class="grid grid-cols-1 md:grid-cols-4 gap-4">
          <div>
            <h3 class="text-lg font-bold mb-2">Cwowd</h3>
            <p class="text-sm">Cwowd est une communauté passionnée de joueurs de jeux de société, partageant des
              analyses, des impressions et des discussions autour de notre passion commune.</p>
          </div>
          <div>
            <h3 class="text-lg font-bold mb-2">Liens rapides</h3>
            <ul>
              <li><a href="#" class="text-sm">Accueil</a></li>
              <li><a href="#" class="text-sm">Articles</a></li>
              <li><a href="#" class="text-sm">Publications</a></li>
            </ul>
          </div>
          <div>
            <h3 class="text-lg font-bold mb-2">Catégories</h3>
            <ul>
              <li><a href="#" class="text-sm">Jeux en financement</a></li>
              <li><a href="#" class="text-sm">Jeux annoncés</a></li>
              <li><a href="#" class="text-sm">Jeux financés</a></li>
            </ul>
          </div>
          <div>
            <h3 class="text-lg font-bold mb-2">Nous suivre</h3>
            <div class="flex space-x-2">
              <a href="#" class="text-sm">Facebook</a>
              <a href="#" class="text-sm">Twitter</a>
              <a href="#" class="text-sm">Instagram</a>
            </div>
            <div class="mt-4">
              <h4 class="text-md font-bold mb-2">Inscrivez-vous à notre newsletter</h4>
              <input type="email" placeholder="Votre email"
                class="px-2 py-1 rounded-md border border-gray-300 text-black">
              <button class="primary text-white px-4 py-1 rounded-md">S'inscrire</button>
            </div>
          </div>
        </div>
        <div class="text-center mt-4">
          <p class="text-sm">© 2025 Cwowd.com</p>
        </div>
      </div>
    </footer>
  </div>
</template>
