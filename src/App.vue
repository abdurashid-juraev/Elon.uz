<script setup>
import { ref } from "vue";
// @ts-ignore
import { RouterLink, RouterView } from "vue-router";
// @ts-ignore
import Header from "@/components/layout/TheHeader.vue";
// @ts-ignore
import Footer from "@/components/layout/TheFooter.vue";
// @ts-ignore
import MainInput from "@/components/MainInput.vue";
// @ts-ignore
import CategoryCard from "@/components/CategoryCard.vue";

import ctg from "./data/category.json";

const ctgs = ref(ctg);
</script>

<template>
  <div class="flex h-screen flex-col justify-between">
    <div>
      <Header />
      <MainInput />
      <section class="mb-6 pt-6">
        <div class="container mx-auto">
          <h2 class="mb-8 text-center text-3xl font-semibold">
            Главные категории
          </h2>
          <div class="grid grid-cols-9">
            <CategoryCard
              v-for="ctg in ctgs"
              :key="ctg.id"
              :img="ctg.img"
              :title="ctg.title"
              :bgColor="ctg.bgColor"
            />
          </div>
        </div>
      </section>
      <section class="mb-6 bg-gray-100 pt-6">
        <div class="container mx-auto">
          <h2 class="mb-8 text-center text-3xl font-semibold">
            Премиум объявления
          </h2>
        </div>
      </section>
    </div>
    <RouterView />
    <Footer />
  </div>
</template>
<style>
.bg-blue-500
  .bg-yellow-300
  .bg-teal-300
  .bg-red-500
  .bg-yellow-100
  .bg-cyan-400
  .bg-blue-300
  .bg-red-200
  .bg-blue-200 {
  color: inherit;
}
</style>
