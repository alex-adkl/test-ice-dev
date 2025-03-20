<template>
  <!-- fond dégradé -->
  <div
    class="relative bg-gradient-to-b from-green-100 to-neutral-50 min-h-[250px] md:min-h-[300px] flex flex-col justify-center items-center p-8 w-full"
  >
    <!-- petite pointe sous le fond dégradé -->
    <div
      class="absolute bottom-[-2.5rem] left-1/2 transform -translate-x-1/2 w-[7.625rem] h-[2.5rem] bg-neutral-50 clip-triangle"
    ></div>

    <!-- titre -->
    <div class="top-container">
      <h1 class="text-4xl font-black text-gray-700">Les patients du cabinet</h1>
    </div>

    <!-- boutons -->
    <div
      class="mt-8 flex flex-col md:flex-row flex-wrap justify-center items-center gap-6 w-full"
    >
      <button class="btn-primary">
        <img
          src="@/assets/icons/Add-patient-white-icon.svg"
          class="icon"
          alt="Ajouter un patient"
        />
        <span class="text">Ajouter<br />un patient</span>
      </button>

      <button class="btn-primary">
        <img
          src="@/assets/icons/Queued-patient-white-icon.svg"
          class="icon"
          alt="Patients en attente"
        />
        <span class="text">Patients<br />en attente</span>
      </button>

      <button class="btn-outline">
        <img
          src="@/assets/icons/Archived-patient-green-icon.svg"
          class="icon"
          alt="Patients archivés"
        />
        <span class="text">Patients<br />archivés</span>
      </button>

      <button class="btn-outline">
        <img
          src="@/assets/icons/View-caregivers-green-icon.svg"
          class="icon"
          alt="Voir les aidants"
        />
        <span class="text">Voir les<br />aidants</span>
      </button>
    </div>
  </div>
</template>

<style scoped>
.clip-triangle {
  clip-path: polygon(50% 100%, 0 0, 100% 0);
}

/* boutons verts */
.btn-primary {
  @apply flex flex-row items-center justify-center w-[13.5rem] h-[5rem]
           px-6 py-2 text-white font-nunito font-extrabold text-lg 
           rounded-full bg-emerald-400 leading-tight gap-5;
}

/* boutons contour vert */
.btn-outline {
  @apply flex flex-row items-center justify-center w-[13.5rem] h-[5rem]
           px-6 py-2 text-emerald-400 font-nunito font-extrabold text-lg 
           rounded-full border-2 border-emerald-400 leading-tight gap-5;
}

/* icones alignées */
.icon {
  @apply w-[2.56rem] h-[2.56rem] flex-shrink-0;
}

.text {
  @apply text-left pl-2;
}

.top-container {
  margin-top: 0;
  padding-top: 0;
}
</style>
