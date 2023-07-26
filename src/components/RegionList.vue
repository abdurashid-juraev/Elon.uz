<template>
  <div class="absolute left-0 right-0 top-full ml-0 mt-2 w-full bg-gray-100">
    <div class="grid grid-cols-3">
      <ul class="">
        <li
          v-for="region in regions.slice(0, 5)"
          :key="region.id"
          class="flex items-center justify-between px-5 py-4 duration-150 hover:bg-slate-200"
        >
          <a href="#!">
            {{ region.name }}
          </a>
          <img src="../assets//icons/arrow.svg" alt="" />
        </li>
      </ul>
      <ul class="">
        <li
          v-for="region in regions.slice(5, 10)"
          :key="region.id"
          class="flex items-center justify-between px-5 py-4 duration-150 hover:bg-slate-200"
        >
          <a href="#!">
            {{ region.name }}
          </a>
          <img src="../assets//icons/arrow.svg" alt="" />
        </li>
      </ul>
      <ul class="">
        <li
          v-for="region in regions.slice(10, 15)"
          :key="region.id"
          class="flex items-center justify-between px-5 py-4 duration-150 hover:bg-slate-200"
        >
          <a href="#!">
            {{ region.name }}
          </a>
          <img src="../assets//icons/arrow.svg" alt="" />
        </li>
      </ul>
    </div>
  </div>
</template>

<script setup>
import { ref, computed } from "vue";
import reg from "../data/regions.json";
const regions = ref(reg);
regions.value.sort((a, b) => {
  let count = 0;
  if (a.name < b.name) {
    count = -1;
  } else if (a.name > b.name) {
    count = 1;
  }
  return count;
});
</script>
