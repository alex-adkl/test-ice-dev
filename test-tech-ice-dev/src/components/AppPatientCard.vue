<script setup>
defineProps({
  name: String,
  age: Number,
  phone: String,
  email: String,
  address: String,
  avatar: String,
  isGreenCard: Boolean, // alternance des couleurs basée sur l'index
});
</script>

<template>
  <div
    class="relative flex flex-col items-center w-full max-w-[21rem] h-[22rem] p-5 rounded-xl text-center mt-[6rem] border-2"
    :class="
      isGreenCard
        ? 'bg-green-100 border-green-100'
        : 'bg-white border-emerald-400'
    "
  >
    <div
      class="absolute top-[-7.5rem] bg-emerald-200 rounded-full flex justify-center items-center w-[10rem] h-[10rem]"
    >
      <img :src="avatar" class="w-full rounded-full" :alt="name" />
    </div>

    <div class="mt-[3.75rem]">
      <h2 class="text-emerald-400 text-lg font-black leading-relaxed">
        {{ name }}
      </h2>
      <p class="text-gray-700 text-sm mb-2 leading-relaxed">{{ age }} ans</p>
      <div class="line w-[100%] h-[0.0625rem] bg-gray-300 my-2"></div>

      <div class="mt-3 space-y-3 text-left">
        <div
          class="text-gray-700 flex items-center gap-3 text-lg font-extrabold leading-relaxed"
        >
          <img
            src="@/assets/icons/Phone-green-icon.svg"
            alt="Phone"
            class="w-[1.2rem] h-[1.2rem]"
          />
          <span>{{ phone }}</span>
        </div>
        <div
          class="text-gray-700 flex items-center gap-3 text-lg font-extrabold leading-relaxed"
        >
          <img
            src="@/assets/icons/Mail-green-icon.svg"
            alt="Email"
            class="w-[1.2rem] h-[1.2rem]"
          />
          <span>{{ email }}</span>
        </div>
        <div
          class="text-gray-700 flex items-start gap-3 text-lg font-extrabold leading-relaxed"
        >
          <img
            src="@/assets/icons/Map-green-icon.svg"
            alt="Address"
            class="w-[1.2rem] h-[1.2rem] self-start mt-1"
          />
          <span>{{ address }}</span>
        </div>
        <div
          class="text-gray-700 flex items-center gap-3 text-lg font-extrabold leading-relaxed"
        >
          <img
            src="@/assets/icons/Plus-icon.svg"
            alt="Ordonnances"
            class="w-[1.2rem] h-[1.2rem]"
          />
          <span>Voir ses ordonnances</span>
        </div>
      </div>
    </div>
  </div>
</template>
