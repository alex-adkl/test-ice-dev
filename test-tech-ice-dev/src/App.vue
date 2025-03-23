<script setup>
import { ref } from "vue";

import AppHeader from "@/components/AppHeader.vue";
import AppPatientCard from "@/components/AppPatientCard.vue";
import AppTop from "@/components/AppTop.vue";
import AppSearch from "@/components/AppSearch.vue";
import AppMenu from "@/components/AppMenu.vue";
const avatar1 = new URL(
  "@/assets/images/Avatar-patiente-1.svg",
  import.meta.url
).href;
const avatar2 = new URL(
  "@/assets/images/Avatar-patiente-2.svg",
  import.meta.url
).href;
const avatar3 = new URL(
  "@/assets/images/Avatar-patiente-3.svg",
  import.meta.url
).href;
const avatar4 = new URL(
  "@/assets/images/Avatar-patiente-4.svg",
  import.meta.url
).href;
const avatar5 = new URL(
  "@/assets/images/Avatar-patiente-5.svg",
  import.meta.url
).href;

const patients = [
  {
    name: "Cécile Moulin",
    age: 81,
    phone: "04 77 36 65 95",
    email: "cecilemoulin@gmail.com",
    address: "16 rue Maurice Bouchor \n69007 Lyon",
    avatar: avatar1,
  },
  {
    name: "Juliette Masselis",
    age: 39,
    phone: "04 77 36 65 95",
    email: "cecilemoulin@gmail.com",
    address: "16 rue Maurice Bouchor \n69007 Lyon",
    avatar: avatar3,
  },
  {
    name: "René Guitay",
    age: 81,
    phone: "04 77 36 65 95",
    email: "cecilemoulin@gmail.com",
    address: "16 rue Maurice Bouchor \n69007 Lyon",
    avatar: avatar2,
  },
  {
    name: "Clara Camalet",
    age: 31,
    phone: "04 77 36 65 95",
    email: "cecilemoulin@gmail.com",
    address: "16 rue Maurice Bouchor \n69007 Lyon",
    avatar: avatar4,
  },
  {
    name: "Lola Dufour",
    age: 81,
    phone: "04 77 36 65 95",
    email: "cecilemoulin@gmail.com",
    address: "16 rue Maurice Bouchor \n69007 Lyon",
    avatar: avatar1,
  },
  {
    name: "Etienne Morlé",
    age: 81,
    phone: "04 77 36 65 95",
    email: "cecilemoulin@gmail.com",
    address: "16 rue Maurice Bouchor \n69007 Lyon",
    avatar: avatar5,
  },
];
</script>

<template>
  <div class="app-container">
    <AppMenu />

    <div class="content">
      <AppHeader />

      <main class="page-content">
        <AppTop />
        <AppSearch />
        <div class="card-container">
          <div class="patients">
            <AppPatientCard
              v-for="(patient, index) in patients"
              :key="index"
              :name="patient.name"
              :age="patient.age"
              :phone="patient.phone"
              :email="patient.email"
              :address="patient.address"
              :avatar="patient.avatar"
              :isGreenCard="index % 2 === 0"
            />
          </div>
        </div>
      </main>
    </div>
  </div>
</template>

<style scoped>
.page-content {
  margin-top: 0.5rem;
  padding-top: 0rem;
}
.patients {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 2rem;
  row-gap: 5rem;
  white-space: pre-line;
}
.card-container {
  padding-left: 6rem;
  padding-right: 6rem;
  padding-bottom: 8rem;
}
@media (min-width: 768px) {
  .content {
    padding-left: 16rem;
    padding-bottom: 8rem;
  }
}
</style>
