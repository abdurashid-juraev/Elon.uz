<template>
  <header class="py-2 bg-gray-100 mb-8">
    <nav class="container mx-auto">
      <div class="flex justify-between items-center">
        <a href="#!" class="font-sans font-semibold text-3xl">Elon.uz</a>
        <div>
          <ul class="flex items-center">
            <li class="ml-3 group">
              <a href="#!" class="flex items-center">
                <img class="mr-2" src="@/assets/icons/sms.svg" alt="" />
                <span class="group-hover:text-blue-500">Сообщения </span>
              </a>
            </li>
            <li class="flex items-center ml-5">
              <a href="#!" class="mr-2 hover:text-blue-500">O'Z</a
              ><span
                class="border-r-2 h-4 mr-2 border-gray-600 border-solid"
              ></span>
              <a href="#!" class="hover:text-blue-500">Рус</a>
            </li>
            <li class="ml-5">
              <a href="#!" class="flex items-center"
                ><img class="" src="@/assets/icons//heart.svg" alt=""
              /></a>
            </li>
            <li class="ml-5">
              <a href="#!" class="flex items-center group"
                ><img class="mr-2" src="@/assets/icons/person.svg" alt="" />
                <span class="group-hover:text-blue-500">Ваш профиль</span>
              </a>
            </li>
            <li class="ml-4">
              <button
                class="py-3 px-5 border border-solid border-gray-400 rounded-md hover:border-slate-200 hover:bg-slate-200 tran duration-150"
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

<script setup></script>
