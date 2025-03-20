<script setup>
import { ref } from "vue";
import patientIcon from "@/assets/icons/Patient-black-icon.svg";
import arrowUpBlack from "@/assets/icons/Arrow-up-black-icon.svg";
import arrowDownWhite from "@/assets/icons/Arrow-down-white-icon.svg";
import pharmacy from "@/assets/icons/Pharmacy-black-icon.svg";
import prescription from "@/assets/icons/Prescription-black-icon.svg";
import home from "@/assets/icons/Home-black-icon.svg";
import pill from "@/assets/icons/Pill-black-icon.svg";
import documents from "@/assets/icons/Documents-black-icon.svg";
import stethoscope from "@/assets/icons/Stethoscope-black-icon.svg";

const isMenuOpen = ref(false);

// gestion des menus déroulants
const menuItems = ref([
  { text: "Accueil", link: "#", icon: home, isOpen: false },
  {
    text: "Mes ordonnances",
    link: "#",
    icon: prescription,
    isOpen: false,
  },
  {
    text: "Mes patients",
    link: "#",
    icon: patientIcon,
    isOpen: false,
    children: [
      { text: "Tous les patients", link: "#" },
      { text: "Patients en attente", link: "#" },
      { text: "Patients archivés", link: "#" },
    ],
  },
  {
    text: "Mes pharmacies",
    link: "#",
    icon: pharmacy,
    isOpen: false,
  },
  {
    text: "Mes documents",
    link: "#",
    icon: documents,
    isOpen: false,
    children: [
      { text: "Ordonnances", link: "#" },
      { text: "Résultats d'analyse", link: "#" },
    ],
  },
  { text: "Mes Pilbeez", link: "#", icon: pill, isOpen: false },
  {
    text: "Parrainer un cabinet",
    link: "#",
    icon: stethoscope,
    isOpen: false,
  },
]);

const toggleMenu = (selectedItem) => {
  menuItems.value.forEach((item) => {
    if (item !== selectedItem) {
      item.isOpen = false; // ferme toutes les autres rubriques
    }
  });
  selectedItem.isOpen = !selectedItem.isOpen; // change seulement l'état de l'item cliqué
};
</script>

<template>
  <!-- MENU MOBILE -->
  <div
    class="fixed bottom-0 left-0 w-full h-[5rem] bg-emerald-400 flex md:hidden items-center z-50 shadow-md"
  >
    <!-- bouton hamburger -->
    <button @click="isMenuOpen = !isMenuOpen" class="px-6 py-4">
      <img
        src="@/assets/icons/Menu-white-icon.svg"
        alt="Menu"
        class="w-8 h-8"
      />
    </button>

    <!-- trait blanc vertical -->
    <div class="h-full w-[2px] bg-white"></div>

    <!-- bloc jaune points -->
    <div
      class="h-full bg-yellow-400 px-4 flex flex-col justify-center items-center text-gray-700 ml-auto"
    >
      <span class="text-3xl text-white font-black leading-none">1740</span>
      <span class="text-base font-bold">points</span>
    </div>
  </div>

  <!-- MENU DÉROULANT MOBILE -->
  <div
    v-if="isMenuOpen"
    class="fixed inset-0 bg-gray-700 bg-opacity-50 z-50 flex flex-col items-center pt-20"
  >
    <div class="bg-white w-64 p-6 rounded-lg shadow-lg">
      <ul class="space-y-4">
        <li v-for="item in menuItems" :key="item.text">
          <a
            :href="item.link"
            class="block p-3 rounded-md text-emerald-600 hover:bg-emerald-200"
          >
            {{ item.text }}
          </a>
        </li>
      </ul>
      <!-- bouton fermeture du menu -->
      <button
        @click="isMenuOpen = false"
        class="mt-4 text-emerald-600 font-bold"
      >
        Fermer
      </button>
    </div>
  </div>

  <!-- MENU SIDEBAR (vue DESKTOP) -->
  <nav
    class="hidden md:flex flex-col fixed top-0 left-0 w-64 h-screen bg-emerald-400 p-6 text-white z-40 pt-[3.5rem]"
  >
    <ul class="space-y-2 flex-grow overflow-auto">
      <li v-for="item in menuItems" :key="item.text">
        <div
          class="flex items-center justify-between p-3 rounded-md hover:bg-emerald-400 cursor-pointer"
          @click="toggleMenu(item)"
        >
          <div class="flex items-center gap-3">
            <img v-if="item.isOpen" :src="item.icon" alt="" class="w-3 h-3" />
            <span
              :class="{
                'text-gray-700 font-black': item.isOpen,
                'text-white font-black': !item.isOpen,
              }"
            >
              {{ item.text }}
            </span>
          </div>
          <img
            v-if="item.children"
            :src="item.isOpen ? arrowUpBlack : arrowDownWhite"
            alt="Chevron"
            class="w-3 h-3"
          />
        </div>

        <!-- sous menus -->
        <ul v-if="item.isOpen && item.children" class="ml-[2.1rem] space-y-2">
          <li v-for="subItem in item.children" :key="subItem.text">
            <a
              :href="subItem.link"
              class="block text-xs font-black text-white hover:bg-emerald-400 px-1"
            >
              {{ subItem.text }}
            </a>
          </li>
        </ul>
      </li>
    </ul>

    <!-- bloc flottant blanc en bas -->
    <div
      class="fixed bottom-6 left-0 bg-white p-3 w-[7.5rem] rounded-r-full flex justify-center items-center gap-4 flex-shrink-0 z-[999]"
    >
      <img
        src="@/assets/icons/Phone-black-icon.svg"
        alt="Phone"
        class="w-5 h-5"
      />
      <img
        src="@/assets/icons/Mail-black-icon.svg"
        alt="Mail"
        class="w-5 h-5"
      />
    </div>
  </nav>
</template>

<style scoped>
@media (min-width: 768px) {
  nav {
    top: 6rem;
  }
}
</style>
