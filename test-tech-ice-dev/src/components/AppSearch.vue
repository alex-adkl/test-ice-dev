<script setup>
import searchIllustration from "@/assets/images/Search-illustration.svg";
</script>

<template>
  <div class="search-container">
    <div
      class="relative flex flex-col md:flex-row items-center justify-center bg-white p-6 md:p-12 rounded-lg w-full"
    >
      <!-- illustration (visible si largeur > 1200px) -->
      <img
        :src="searchIllustration"
        alt="Illustration Recherche"
        class="hidden xl:block w-[11rem] h-[11rem] lg:w-[9rem] lg:h-[9rem] xl:w-[10rem] xl:h-[10rem] absolute left-[12%] md:ml-[-1rem]"
      />

      <!-- texte + input -->
      <div class="text-center md:w-full md:max-w-lg mx-auto">
        <h2 class="text-emerald-400 font-black text-3xl md:text-3xl">
          Recherchez un patient
        </h2>
        <p class="text-gray-500 text-sm md:text-base mt-2">
          Entrez les premières lettres de nom du patient que vous recherchez.
        </p>
        <div class="mt-4 flex justify-center">
          <input
            type="text"
            placeholder="Nom du patient"
            class="w-full md:w-80 p-3 rounded-full border border-gray-300 focus:outline-none focus:ring-2 focus:ring-emerald-400 text-gray-700 font-black text-center"
          />
        </div>
      </div>
    </div>
    <div class="line w-[80%] h-[0.0625rem] bg-gray-300 my-2 mx-auto"></div>
  </div>
</template>

<style scoped>
/* masque l'illustration si le composant < 1200px */
@media (max-width: 1203px) {
  img {
    display: none;
  }
}
.search-container {
  margin-top: 3rem;
  margin-bottom: 5rem;
}

.line {
  margin-top: 2rem;
}
</style>
