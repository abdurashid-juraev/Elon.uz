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
import PosterCard from "./components/PosterCard.vue";
import ctg from "./data/category.json";
import post from "./data/poster.json";

const ctgs = ref(ctg);
const posts = ref(post);
</script>

<template>
  <div class="flex h-screen flex-col justify-between">
    <div>
      <Header />
      <MainInput />
      <section class="mb-6 py-6">
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
      <section class="mb-6 bg-gray-100 py-8">
        <div class="container mx-auto">
          <h2 class="mb-8 text-center text-3xl font-semibold">
            Премиум объявления
          </h2>
          <div class="grid grid-cols-4 gap-5">
            <PosterCard
              v-for="post in posts"
              :key="post.id"
              :img="post.img"
              :title="post.title"
              :location="post.location"
              :time="post.time"
              :sum="post.sum"
            />
          </div>
        </div>
      </section>
      <section class="mb-6 py-6">
        <div class="container mx-auto">
          <div class="mx-auto flex w-[950px] items-center justify-between">
            <div><img src="./assets/icons/biznes-logo.svg" alt="" /></div>
            <h3 class="text-2xl font-semibold">
              Начните бизнес в интернете с Elon.uz
            </h3>
            <a
              href="#!"
              class="rounded-md border border-solid border-gray-400 px-5 py-3 font-semibold text-black duration-150 hover:border-slate-200 hover:bg-slate-200"
            >
              <span class="mr-2 font-semibold text-black">Подробнее</span>
            </a>
          </div>
        </div>
      </section>
      <section class="mb-8 bg-gray-100 py-9">
        <div class="container mx-auto">
          <h2 class="mb-8 text-center text-5xl font-bold">Elon.uz</h2>
          <p class="mx-auto w-[1100px] text-center text-xl font-semibold">
            Cервис объявлений № 1 в Узбекистане Частные объявления Узбекистана
            на OLX (бывший torg.uz) - здесь вы найдете то, что искали. Нажав на
            кнопку "Подать объявление", вы сможете разместить онлайн-объявление
            на любую необходимую тематику - поиск работы, услуги, продажа
            автомобилей, недвижимости, электроники и многое другое. С помощью
            сервиса OLX в Узбекистане вы можете найти, продать или купить
            практически все, что угодно. Воспользовавшись функцией поиска, вы
            без труда найдете уже опубликованные объявления интересующей вас
            тематики. OLX в Узбекистане - ваш надежный и незаменимый помощник.
          </p>
        </div>
      </section>
      <div class="container mx-auto mb-10 py-10">
        <div>
          <img
            class="object-cover object-center"
            src="./assets/png/poster.jpg"
            alt=""
          />
        </div>
      </div>
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
