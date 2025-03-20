<script setup>
import { ref } from "vue";
import avatarInfirmier from "@/assets/images/Avatar-Infirmier.svg";
</script>

<template>
  <header
    class="fixed top-0 left-0 w-full bg-white flex justify-between items-center p-4 z-50"
  >
    <a href="https://www.ice-dev.com/" target="_blank">
      <img
        src="@/assets/images/Logo.svg"
        class="h-12 md:h-14"
        alt="logo Polo"
      />
    </a>

    <div href="#" class="avatar-container flex flex-row items-center gap-3">
      <div
        class="text-gray-700 text-sm font-black text-right leading-tight hidden md:block"
      >
        Lola<br />Dufour
      </div>
      <img
        src="@/assets/images/Avatar-Infirmier.svg"
        class="avatar-image h-9"
        alt="votre profil"
      />
      <img
        src="@/assets/icons/Arrow-down-icon.svg"
        class="arrow-icon h-2 hidden md:block"
        alt="flèche vers le bas"
      />
    </div>
  </header>
</template>

<style scoped>
header {
  height: 95px;
  max-height: 109px;
}
.avatar-container {
  padding-right: 1rem;
}
</style>
