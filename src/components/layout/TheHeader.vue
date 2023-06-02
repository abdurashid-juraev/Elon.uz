<template>
  <header class="mb-8 bg-gray-100 py-2">
    <nav class="container mx-auto">
      <div class="flex items-center justify-between">
        <a href="#!" class="font-sans text-3xl font-semibold">Elon.uz</a>
        <div>
          <ul class="flex items-center">
            <li class="group ml-3">
              <router-link :to="{ name: 'register' }" class="flex items-center">
                <img class="mr-2" src="@/assets/icons/sms.svg" alt="" />
                <span class="group-hover:text-blue-500">Сообщения </span>
              </router-link>
            </li>
            <li class="ml-5 flex items-center">
              <a href="#!" class="mr-2 hover:text-blue-500">O'Z</a
              ><span
                class="mr-2 h-4 border-r-2 border-solid border-gray-600"
              ></span>
              <a href="#!" class="hover:text-blue-500">Рус</a>
            </li>
            <li class="ml-5">
              <a href="#!" class="flex items-center"
                ><img class="" src="@/assets/icons//heart.svg" alt=""
              /></a>
            </li>
            <li class="ml-5">
              <a href="#!" class="group flex items-center"
                ><img class="mr-2" src="@/assets/icons/person.svg" alt="" />
                <span class="group-hover:text-blue-500">Ваш профиль</span>
              </a>
            </li>
            <li class="ml-4">
              <button
                class="rounded-md border border-solid border-gray-400 px-5 py-3 font-semibold text-black duration-150 hover:border-slate-200 hover:bg-slate-200"
              >
                Подать объявление
              </button>
            </li>
          </ul>
        </div>
      </div>
    </nav>
  </header>
</template>

<script setup>
// @ts-ignore
import { RouterLink } from "vue-router";
</script>
