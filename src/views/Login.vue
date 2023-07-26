<template>
  <div class="container mx-auto">
    <div class="flex h-screen items-center justify-center">
      <div class="w-96">
        <a
          href="#!"
          class="mb-4 flex items-center justify-center px-7 py-4 outline outline-2 duration-75 hover:outline-4"
        >
          <img
            class="mr-4 h-8 w-8 object-cover object-center"
            src="@/assets/icons/google.svg"
            alt=""
          />
          <span class="text-xl font-semibold">Продолжить через Google</span>
        </a>
        <div class="mb-2 flex items-center">
          <span class="block h-[1px] w-full bg-black"></span
          ><span class="mx-3 text-sm font-semibold">ИЛИ</span
          ><span class="block h-[1px] w-full bg-black"></span>
        </div>
        <div class="mb-5 grid grid-cols-2 gap-2">
          <router-link
            :to="{ name: 'login' }"
            class="border-b-2 border-black pb-3 font-semibold duration-200 text-center"
            >Войти</router-link
          >
          <router-link :to="{ name: 'register' }" class="pb-3 text-center"
            >Зарегистрироваться</router-link
          >
        </div>
        <MainForm />
      </div>
    </div>
  </div>
</template>

<script setup>
import { RouterLink } from "vue-router";
// @ts-ignore
import MainForm from "../components/MainForm.vue";
</script>
