<template>
  <article class="rounded-md bg-white p-5">
    <a href="#!" class="mb-4 block h-72 overflow-hidden">
      <img
        class="h-full w-full object-cover object-center"
        :src="`src/assets/icons/${img}`"
        alt=""
      />
    </a>
    <div>
      <h3 class="mb-6 line-clamp-2 text-xl">
        {{ title }}
        <!-- Компрессор Воздушный SAAB 100 л 10 bar -->
      </h3>
      <div class="mb-3 flex flex-wrap items-center">
        <div class="line-clamp-1 text-sm">
          {{ location }}
          <!-- Ташкент, Юнусабадский район -->
        </div>
        <span class="mx-1">-</span>
        <div class="text-sm">
          {{ time }}
          <!-- Сегодня 07:50 -->
        </div>
      </div>
      <div class="flex items-center justify-between">
        <div class="text-2xl font-semibold">
          {{ sum }}
          <!-- 3 850 000  -->
          сум
        </div>
        <div>
          <svg
            width="24px"
            class="duration-150 hover:stroke-red-500"
            height="24px"
            viewBox="0 0 50 50"
          >
            <g id="Layer_1">
              <path
                d="M45.281,25.915c4.949-5.004,4.949-13.146,0-18.15C42.881,5.337,39.688,4,36.292,4c-0.001,0-0.001,0-0.001,0
		c-3.396,0-6.59,1.337-8.991,3.765L25,10.09l-2.3-2.325C20.299,5.337,17.106,4,13.709,4c-3.396,0-6.589,1.337-8.99,3.765
		c-4.949,5.004-4.949,13.146,0,18.15L25,46.422L45.281,25.915z M6.141,9.171C8.163,7.126,10.852,6,13.709,6
		c2.858,0,5.547,1.126,7.569,3.171L25,12.935l3.722-3.764C30.744,7.126,33.433,6,36.291,6c2.858,0,5.546,1.126,7.568,3.171
		c4.183,4.229,4.183,11.109,0,15.338L25,43.578L6.141,24.509C1.958,20.28,1.958,13.399,6.141,9.171z"
              />
            </g>
            <g></g>
          </svg>
        </div>
      </div>
    </div>
  </article>
</template>

<script setup>
// @ts-ignore
import { defineProps } from "vue";

const props = defineProps(["img", "title", "location", "time", "sum"]);
</script>
