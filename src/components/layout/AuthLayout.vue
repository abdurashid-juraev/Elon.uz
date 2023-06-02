<template>
  <div class="container mx-auto">
    <div class="flex h-screen items-center justify-center">
      <div class="">
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
          <button class="border-b-2 border-black text-center">Войти</button
          ><button class="text-center">Зарегистрироваться</button>
        </div>
        <form action="" class="flex flex-col">
          <label for="" class="mb-3">
            <div class="mb-2">Электронная почта или телефон</div>
            <input
              type="text"
              class="w-full rounded bg-gray-100 p-2 focus:outline-2 focus:outline-gray-300"
            />
          </label>
          <label for="">
            <div class="mb-2">Пароль</div>
            <div class="relative">
              <input
                :type="inputType"
                class="w-full rounded bg-gray-100 p-2 focus:outline-2 focus:outline-gray-300"
              />
              <button
                type="button"
                @click="showHide"
                class="absolute bottom-0 right-4 top-0 my-auto cursor-pointer"
              >
                <img v-show="visible1" src="@/assets/icons/eye.svg" alt="" />
                <img
                  v-show="visible2"
                  src="@/assets/icons/eyelock.svg"
                  alt=""
                />
              </button>
            </div>
          </label>
        </form>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";
let visible1 = ref(true);
let visible2 = ref(false);
const inputType = ref("text");

function changeInputType(){
  if (inputType.value === "text") {
    inputType.value = "password";
  } else if (inputType.value === "password") {
    inputType.value = "text";
  }
}
const showHide = () => {
  changeInputType()
};
</script>
