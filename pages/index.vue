<template>
  <div class="relative bg-white overflow-hidden">
    <!-- Background Patterns -->
    <div class="hidden lg:block lg:absolute lg:inset-0">
      <svg
        class="absolute top-0 left-1/2 transform translate-x-64 -translate-y-8"
        width="640"
        height="784"
        fill="none"
        viewBox="0 0 640 784"
      >
        <defs>
          <pattern
            id="9ebea6f4-a1f5-4d96-8c4e-4c2abf658047"
            x="118"
            y="0"
            width="20"
            height="20"
            patternUnits="userSpaceOnUse"
          >
            <rect
              x="0"
              y="0"
              width="4"
              height="4"
              class="text-gray-200"
              fill="currentColor"
            />
          </pattern>
        </defs>
        <rect
          y="72"
          width="640"
          height="640"
          class="text-gray-50"
          fill="currentColor"
        />
        <rect
          x="118"
          width="404"
          height="784"
          fill="url(#9ebea6f4-a1f5-4d96-8c4e-4c2abf658047)"
        />
      </svg>
    </div>

    <div class="relative pt-6 pb-16 md:pb-20 lg:pb-24 xl:pb-32">
      <!-- Navigation -->
      <nav
        class="relative max-w-screen-xl mx-auto flex items-center justify-between px-4 sm:px-6"
      >
        <div class="flex items-center flex-1">
          <div class="flex items-center justify-between w-full md:w-auto">
            <a href="#" aria-label="Home">
              <img class="h-20 w-auto sm:h-24" src="/logo.png" alt="Logo" />
            </a>
            <div class="-mr-2 flex items-center md:hidden">
              <button
                id="main-menu"
                type="button"
                class="inline-flex items-center justify-center p-2 rounded-md text-gray-400 hover:text-gray-500 hover:bg-gray-100 focus:outline-none focus:bg-gray-100 focus:text-gray-500 transition duration-150 ease-in-out"
                aria-label="Main menu"
                aria-haspopup="true"
              >
                <svg
                  class="h-6 w-6"
                  stroke="currentColor"
                  fill="none"
                  viewBox="0 0 24 24"
                >
                  <path
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    stroke-width="2"
                    d="M4 6h16M4 12h16M4 18h16"
                  />
                </svg>
              </button>
            </div>
          </div>
          <div class="hidden md:block md:ml-10">
            <a
              href="#"
              class="font-medium text-gray-500 hover:text-gray-900 transition duration-150 ease-in-out"
              >Blog</a
            >
            <a
              href="#"
              class="ml-10 font-medium text-gray-500 hover:text-gray-900 transition duration-150 ease-in-out"
              >Références</a
            >
            <a
              href="#"
              class="ml-10 font-medium text-gray-500 hover:text-gray-900 transition duration-150 ease-in-out"
              >Compétences</a
            >
            <a
              href="#"
              class="ml-10 font-medium text-gray-500 hover:text-gray-900 transition duration-150 ease-in-out"
              >Réseaux</a
            >
          </div>
        </div>
        <div class="hidden md:block text-right">
          <span class="inline-flex rounded-md shadow-md">
            <span class="inline-flex rounded-md shadow-xs">
              <a
                href="#"
                class="inline-flex items-center px-4 py-2 border border-transparent text-base leading-6 font-medium rounded-md text-indigo-600 bg-white hover:bg-gray-50 focus:outline-none focus:border-indigo-300 focus:shadow-outline-indigo transition duration-150 ease-in-out"
              >
                Contact
              </a>
            </span>
          </span>
        </div>
      </nav>

      <!--
      Mobile menu, show/hide based on menu open state.

      Entering: "duration-150 ease-out"
        From: "opacity-0 scale-95"
        To: "opacity-100 scale-100"
      Leaving: "duration-100 ease-in"
        From: "opacity-100 scale-100"
        To: "opacity-0 scale-95"
    -->
      <div
        class="absolute top-0 inset-x-0 p-2 transition transform origin-top-right md:hidden"
      >
        <div class="rounded-lg shadow-md">
          <div
            class="rounded-lg bg-white shadow-xs overflow-hidden"
            role="menu"
            aria-orientation="vertical"
            aria-labelledby="main-menu"
          >
            <div class="px-5 pt-4 flex items-center justify-between">
              <div>
                <img
                  class="h-8 w-auto"
                  src="https://tailwindui.com/img/logos/workflow-mark-on-white.svg"
                  alt=""
                />
              </div>
              <div class="-mr-2">
                <button
                  type="button"
                  class="inline-flex items-center justify-center p-2 rounded-md text-gray-400 hover:text-gray-500 hover:bg-gray-100 focus:outline-none focus:bg-gray-100 focus:text-gray-500 transition duration-150 ease-in-out"
                  aria-label="Close menu"
                >
                  <svg
                    class="h-6 w-6"
                    stroke="currentColor"
                    fill="none"
                    viewBox="0 0 24 24"
                  >
                    <path
                      stroke-linecap="round"
                      stroke-linejoin="round"
                      stroke-width="2"
                      d="M6 18L18 6M6 6l12 12"
                    />
                  </svg>
                </button>
              </div>
            </div>
            <div class="px-2 pt-2 pb-3">
              <a
                href="#"
                class="block px-3 py-2 rounded-md text-base font-medium text-gray-700 hover:text-gray-900 hover:bg-gray-50 focus:outline-none focus:text-gray-900 focus:bg-gray-50 transition duration-150 ease-in-out"
                role="menuitem"
                >Blog</a
              >
              <a
                href="#"
                class="mt-1 block px-3 py-2 rounded-md text-base font-medium text-gray-700 hover:text-gray-900 hover:bg-gray-50 focus:outline-none focus:text-gray-900 focus:bg-gray-50 transition duration-150 ease-in-out"
                role="menuitem"
                >Références</a
              >
              <a
                href="#"
                class="mt-1 block px-3 py-2 rounded-md text-base font-medium text-gray-700 hover:text-gray-900 hover:bg-gray-50 focus:outline-none focus:text-gray-900 focus:bg-gray-50 transition duration-150 ease-in-out"
                role="menuitem"
                >Compétences</a
              >
              <a
                href="#"
                class="mt-1 block px-3 py-2 rounded-md text-base font-medium text-gray-700 hover:text-gray-900 hover:bg-gray-50 focus:outline-none focus:text-gray-900 focus:bg-gray-50 transition duration-150 ease-in-out"
                role="menuitem"
                >Réseaux</a
              >
            </div>
            <div>
              <a
                href="#"
                class="block w-full px-5 py-3 text-center font-medium text-indigo-600 bg-gray-50 hover:bg-gray-100 hover:text-indigo-700 focus:outline-none focus:bg-gray-100 focus:text-indigo-700 transition duration-150 ease-in-out"
                role="menuitem"
              >
                Contact
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>

    <home-main-content />
  </div>
</template>

<script>
import HomeMainContent from '~/components/HomeMainContent.vue'

export default {
  components: {
    HomeMainContent,
  },
}
</script>
