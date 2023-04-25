<script setup>
import { RouterLink, RouterView } from "vue-router";
// @ts-ignore
import Header from "@/components/layout/TheHeader.vue";
// @ts-ignore
import Footer from "@/components/layout/TheFooter.vue";
// @ts-ignore
import MainInput from "@/components/MainInput.vue";
</script>

<template>
  <div class="flex flex-col justify-between h-screen">
    <Header />
    <MainInput />
    <RouterView />
    <Footer />
  </div>
</template>

<style>
@import url(@/assets/index.css);
</style>
