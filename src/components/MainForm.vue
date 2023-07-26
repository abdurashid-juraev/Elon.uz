<template>
  <form action="" @submit.prevent="submit" class="flex flex-col">
    <label for="" class="mb-3">
      <div class="mb-2">Электронная почта или телефон</div>
      <input
        placeholder="example@gmail.com"
        type="text"
        class="w-full rounded bg-gray-100 p-2 focus:outline-2 focus:outline-gray-300"
      />
    </label>
    <label for="" class="mb-3">
      <div class="mb-2">Пароль</div>
      <div class="relative">
        <input
          :type="inputType"
          v-model="inputField"
          class="w-full rounded bg-gray-100 p-2 focus:outline-2 focus:outline-gray-300"
        />
        <div
          @click="showHideInputToggle"
          class="absolute bottom-0 right-4 top-0 my-auto flex cursor-pointer items-center"
        >
          <div>
            <span v-show="visible">
              <svg
                width="1em"
                height="1em"
                viewBox="0 0 24 24"
                fill="none"
                xmlns="http://www.w3.org/2000/svg"
              >
                <path
                  fill-rule="evenodd"
                  clip-rule="evenodd"
                  d="M9.042 12a3 3 0 1 1 6 0 3 3 0 0 1-6 0Zm2 0c0 .551.449 1 1 1 .55 0 1-.449 1-1 0-.551-.45-1-1-1-.551 0-1 .449-1 1Z"
                  fill="currentColor"
                ></path>
                <path
                  fill-rule="evenodd"
                  clip-rule="evenodd"
                  d="M2 12c1.29-4.047 5.295-7 10.042-7s8.75 2.953 10.042 7c-1.291 4.047-5.295 7-10.042 7S3.29 16.047 2 12Zm2.13 0c1.249 2.974 4.408 5 7.912 5 3.504 0 6.663-2.026 7.912-5-1.25-2.974-4.408-5-7.912-5-3.504 0-6.663 2.026-7.912 5Z"
                  fill="currentColor"
                ></path>
              </svg>
            </span>
            <span v-show="isVisible">
              <svg
                width="1em"
                height="1em"
                viewBox="0 0 24 24"
                xmlns="http://www.w3.org/2000/svg"
              >
                <path
                  d="m3.498 2 3.984 3.985A11.008 11.008 0 0 1 12.042 5c4.747 0 8.75 2.953 10.042 7-.635 1.989-1.928 3.708-3.641 4.946l4.59 4.59v1.414H21.62L2.084 3.415V2h1.414zm1.406 5.637L6.327 9.06a7.797 7.797 0 0 0-2.197 2.939c1.249 2.974 4.408 5 7.912 5 .68 0 1.339-.097 1.982-.242l1.635 1.635a11.073 11.073 0 0 1-3.617.607C7.295 19 3.29 16.047 2 12c.54-1.692 1.559-3.19 2.904-4.363zM12.042 7c-1.051 0-2.06.203-3.004.54l1.742 1.743c.383-.18.81-.283 1.262-.283a3 3 0 0 1 3 3c0 .452-.103.879-.283 1.262l2.228 2.228c1.313-.866 2.367-2.06 2.967-3.49-1.25-2.974-4.408-5-7.912-5zm-2.98 4.796 3.183 3.183c-.068.005-.134.021-.204.021a3 3 0 0 1-3-3c0-.07.016-.136.021-.204z"
                  fill="currentColor"
                  fill-rule="evenodd"
                ></path>
              </svg>
            </span>
          </div>

          <span class="ml-2" v-show="empty">
            <svg
              width="1em"
              height="1em"
              viewBox="0 0 24 24"
              fill="red"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                d="M11 8v5l1 1 1-1V8l-1-1-1 1ZM11 16a1 1 0 1 1 2 0 1 1 0 0 1-2 0Z"
                fill="red"
              ></path>
              <path
                fill-rule="evenodd"
                clip-rule="evenodd"
                d="M12 2C6.486 2 2 6.486 2 12s4.486 10 10 10 10-4.486 10-10S17.514 2 12 2Zm0 18c-4.411 0-8-3.589-8-8s3.589-8 8-8 8 3.589 8 8-3.589 8-8 8Z"
                fill="red"
              ></path>
            </svg>
          </span>
        </div>
      </div>
      <div class="mt-1 text-sm text-red-500" v-show="empty">
        Вы уверены, что это правильный пароль? Он слишком короткий
      </div>
    </label>
    <div class="mt-3"><a href="#!" class="font-semibold hover:text-gray-600 duration-100 ">Забыли пароль?</a></div>
    <p class="text-sm">
      Я соглашаюсь с <a href="#!"><b>Условия использования</b></a>, а также с передачей и обработкой моих данных в OLX. Я подтверждаю своe совершеннолетие и ответственность за размещение объявления
    </p>
    <button
      type="submit"
      @click.prevent="submit"
      class="mt-6 w-full bg-gray-100 py-3 text-xl font-semibold duration-150 hover:bg-gray-200"
    >Войти
    </button>
  </form>
</template>

<script setup>
import { ref, watch } from "vue";
// import FormBtn from "../components/FormBtn.vue";
const inputType = ref("password");
const isVisible = ref(false);
const visible = ref(true);
const inputField = ref("");
const empty = ref(false);

function changeInputType() {
  if (inputType.value === "password") {
    inputType.value = "text";
    visible.value = false;
    isVisible.value = true;
  } else if (inputType.value === "text") {
    inputType.value = "password";
    visible.value = true;
    isVisible.value = false;
  }
}
const showHideInputToggle = () => {
  changeInputType();
};

const submit = watch(inputField, () => {
  // @ts-ignore
  if (inputField.value === "" || inputField.value.length < 6) {
    empty.value = true;
  }
  // @ts-ignore
  if (inputField.value.length > 6) {
    empty.value = false;
  }
});
</script>
