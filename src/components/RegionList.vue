<template>
  <div
    class="absolute left-0 right-0 top-full ml-0 mt-2 w-full bg-gray-100 p-5"
  >
    <ul class="grid grid-cols-3">
      <li v-for="region in regions" :key="region.id" class="mb-4">
        <a href="#!">
          {{ region.name }}
        </a>
      </li>
    </ul>
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
