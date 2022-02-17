<template>
  <div
    id="navbar"
    class="
      px-4
      py-4
      sm:py-6
      bg-white
      shadow
      sm:bg-gray-900 sm:shadow-none
      w-full
      z-10
    "
  >
    <div
      class="
        container
        mx-auto
        flex flex-col
        sm:flex-row
        items-center
        justify-between
      "
    >
      <div class="w-full flex flex-row items-center justify-between">
        <div class="text-3xl font-bold">
          <span class="sm:text-white">Blog</span>
          <span class="text-primary">Elimisha</span>
        </div>
        <div>
          <button v-show="!isVisible" class="sm:hidden" @click="toggle">
            <svg
              class="w-6 h-6"
              fill="none"
              stroke="currentColor"
              viewBox="0 0 24 24"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M4 6h16M4 12h16M4 18h16"
              ></path>
            </svg>
          </button>

          <button v-show="isVisible" class="sm:hidden" @click="toggle">
            <svg
              class="w-6 h-6"
              fill="none"
              stroke="currentColor"
              viewBox="0 0 24 24"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M6 18L18 6M6 6l12 12"
              ></path>
            </svg>
          </button>
        </div>
      </div>
      <div
        class="
          sm:text-white
          mt-4
          sm:nt-0
          w-full
          sm:space-x-4 sm:text-right sm:block
        "
        :class="{ hidden: !isVisible }"
      >
        <Navbarlink to="/articles" label="Articles" />
        <Navbarlink to="/about" label="About" />
        <Navbarlink to="/contact" label="Contact" />
      </div>
    </div>
  </div>
</template>

<script>
import Navbarlink from "./Navbarlink.vue";
import { useToggle } from "@/composables/useToggle";

export default {
  components: {
    Navbarlink,
  },

  props: {},

  setup() {
    let { isVisible, toggle } = useToggle();

    return {
      isVisible,
      toggle,
    };
  },
};
</script>
