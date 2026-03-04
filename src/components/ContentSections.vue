<script setup>
import FeatureBlock from "./FeatureBlock.vue";
import SplitSection from "./SplitSection.vue";

import career from "./images/career.jpg";
import charsonline from "./images/charsonline.png";
import fast from "./images/fast.jpg";
import graphisme from "./images/graphisme.jpg";
import gtaV from "./images/gtaV.svg";
import gtachars from "./images/gtachars.png";
import gtaOnline from "./images/gtaonline.svg";
import menu from "./images/menu.jpeg";
import tunning from "./images/tunning.jpg";
</script>

<template>
  <SplitSection
    bg-image="/firstsectionbg.jpg"
    :logo-src="gtaV"
    logo-alt="Logo GTA V"
    :side-src="gtachars"
    side-alt="Personnages de GTA V"
    title="Bienvenue à Los Santos"
    :paragraphs="[
      'Lorsqu\'un jeune arnaqueur, un braqueur de banque à la retraite et un terrible psychopathe se retrouvent piégés par de grands criminels, le gouvernement américain et l\'industrie du divertissement, ils doivent effectuer une série de braquages pour survivre dans une ville sans pitié où ils ne peuvent faire confiance à personne, et encore moins à leurs compagnons.',
      'Les joueurs de GTAV sur PC peuvent migrer leur progression du mode Histoire, ainsi que leur progression et leurs personnages de GTA Online, vers la nouvelle version améliorée. Les joueurs sur PlayStation 4 ou Xbox One peuvent également migrer leurs progressions du mode Histoire et du mode en ligne vers PlayStation 5 ou Xbox Series X|S via une migration unique.',
    ]"
  />

  <SplitSection
    :reverse="true"
    bg-image="/secondsection.jpg"
    :logo-src="gtaOnline"
    logo-alt="Logo GTA Online"
    :side-src="charsonline"
    side-alt="Personnages GTA Online"
    title="Grand Theft Auto Online"
    :paragraphs="[
      'Découvrez GTA Online, un univers en ligne dynamique et en perpétuelle évolution pouvant accueillir jusqu\'à 30 joueurs, dans lequel vous pourrez passer de petite frappe à dirigeant d\'un véritable empire du crime.',
      'Profitez de nouvelles améliorations puissantes de véhicules et d\'avantages comme l\'éditeur de carrière, ainsi que des améliorations de gameplay, extensions et contenus de GTA Online qui sont disponibles depuis la sortie, accessibles en solo ou entre amis. Préparez des braquages en coopération, disputez des courses casse-cou démentes, essayez-vous à des modes rivalité uniques, ou détendez-vous dans les espaces sociaux comme les boîtes de nuit, les salles d\'arcade, ou lors de soirées dans la suite avec terrasse, des rassemblements de véhicules et bien plus.',
    ]"
  />

  <FeatureBlock
    :image-src="tunning"
    image-alt="Nouveau contenu exclusif"
    title="Nouveau contenu exclusif"
    text="Accédez à Hao's Special Works dans le salon auto de Los Santos, qui propose des améliorations d'élite et des modifications exclusives. Vous pourrez piloter ces véhicules ultraperformants dans des courses et nouveaux contre-la-montre d'HSW et plus."
  />
  <FeatureBlock
    :image-src="career"
    :reverse="true"
    image-alt="Nouvel éditeur de carrière"
    title="Nouvel éditeur de carrière"
    text="Commencez dans GTA Online sur de bonnes bases. Choisissez l'une des quatre carrières proposées : motard, col blanc, patron d'une boîte de nuit ou expert en trafic d'armes, et faites votre choix parmi une liste de propriétés, de véhicules puissants et d'armes pour lancer votre entreprise."
  />
  <FeatureBlock
    :image-src="menu"
    image-alt="Nouveau menu GTA Online"
    title="Nouveau menu"
    text="Accédez immédiatement à tout ce que propose GTA Online depuis le menu principal, comme aux dernières mises à jour les plus populaires."
  />
  <FeatureBlock
    :image-src="graphisme"
    :reverse="true"
    image-alt="Des graphismes exceptionnels"
    title="Des graphismes exceptionnels"
    text="Profitez d'une fidélité et de performances optimisées grâce à de nouveaux modes graphiques permettant de personnaliser votre expérience de jeu, dont des graphismes de haute volée, un taux d'images par seconde amélioré, des textures de meilleure qualité, ainsi que des ombres et des reflets en ray tracing. Et désormais, découvrez des fonctionnalités telles que l'occlusion ambiante et l'illumination globale sur PC, ainsi que la compatibilité avec AMD FSR et NVIDIA DLSS."
  />
  <FeatureBlock
    :image-src="fast"
    image-alt="Chargement accéléré"
    title="Chargement accéléré"
    text="L'accès à Los Santos et Blaine County est plus rapide que jamais grâce aux temps de chargement réduits."
  />
</template>
