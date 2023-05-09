<template>
  <a href="#!" class="mb-6 flex flex-col items-center justify-center">
    <div
      class="mb-5 h-24 w-24 overflow-hidden rounded-full"
      :class="`${bgColor}`"
    >
      <img
        class="h-full w-full object-center"
        :src="`/src/assets/png/${img}`"
        alt=""
      />
    </div>
    <span class="text-xl font-semibold">{{ title }}</span>
  </a>
</template>

<script setup>
// @ts-ignore
import { defineProps } from "vue";

const props = defineProps(["img", "title", "bgColor"]);
</script>
