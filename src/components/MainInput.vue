<template>
  <div class="container mx-auto mb-6 bg-gray-100">
    <div class="rounded-lg ">
      <div class="relative grid w-full grid-cols-7 gap-4">
        <div
          class="pl-6 col-span-4 flex items-center border-r border-solid border-slate-200"
        >
          <img class="mr-3" src="@/assets/icons/search.svg" alt="" />
          <div class="w-full">
            <input
              type="text"
              placeholder="объявлений рядом"
              class="text-3 w-full bg-transparent p-1 font-semibold focus:bg-white focus:outline-none"
            />
          </div>
        </div>
        <div class="col-span-2 flex items-center">
          <img class="mr-3" src="@/assets/icons/loction.svg" alt="" />
          <div class="w-full">
            <input
              @click.stop="getRegion"
              type="text"
              placeholder="Весь Узбекистан"
              class="text-3 w-full bg-transparent p-1 font-semibold focus:bg-white focus:outline-none"
            />
          </div>
        </div>
        <div
          class="col-span-1 rounded-md border border-solid border-gray-400 py-4 duration-150 hover:border-slate-200 hover:bg-slate-200"
        >
          <button class="flex w-full justify-center">
            <span class="mr-2 font-semibold text-black">Поиск</span
            ><img src="@/assets/icons/search.svg" alt="" />
          </button>
        </div>
        <RegionList v-show="show" />
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";
// @ts-ignore
import RegionList from "../components/RegionList.vue";
const show = ref(false);
function getRegion() {
  const body = document.querySelector("body");
  body.addEventListener("click", () => {
    show.value = false;
  });
  show.value = true;
}
</script>
