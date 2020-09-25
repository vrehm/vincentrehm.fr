<template>
  <div>
    <nav
      class="relative max-w-screen-xl mx-auto flex items-center justify-between px-4 sm:px-6"
    >
      <div class="flex items-center flex-1">
        <div class="flex items-center justify-between w-full md:w-auto">
          <the-logo />

          <div
            class="-mr-2 flex items-center md:hidden"
            @click.prevent="mobileNavOpen = !mobileNavOpen"
          >
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

        <!-- Desktop Navbar Links -->
        <div class="hidden md:block md:ml-10">
          <nuxt-link
            v-for="(link, index) in links"
            :key="link.id"
            :to="{ path: link.path, hash: link.hash }"
            :class="{ 'ml-10': index !== 0 }"
            class="font-medium text-gray-500 hover:text-gray-900 transition duration-150 ease-in-out"
            >{{ link.name }}</nuxt-link
          >
        </div>
      </div>

      <div class="hidden md:block text-right">
        <span class="inline-flex rounded-md shadow-md">
          <span class="inline-flex rounded-md shadow-xs">
            <nuxt-link
              to="#contact"
              class="inline-flex items-center px-4 py-2 border border-transparent text-base leading-6 font-medium rounded-md text-indigo-600 bg-white hover:bg-gray-50 focus:outline-none focus:border-indigo-300 focus:shadow-outline-indigo transition duration-150 ease-in-out"
            >
              {{ cta }}
            </nuxt-link>
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
    <transition
      name="fade"
      enter-active-class="duration-200 ease-out"
      enter-class="opacity-0 scale-95"
      enter-to-class="opacity-100 scale-100"
      leave-active-class="duration-100 ease-in"
      leave-class="opacity-100 scale-100"
      leave-to-class="opacity-0 scale-95"
    >
      <div
        v-show="mobileNavOpen"
        v-click-outside="closeMobileNavbar"
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
                <img class="h-8 w-auto" src="/logo.png" alt="Logo" />
              </div>
              <div
                class="-mr-2"
                @click.prevent="mobileNavOpen = !mobileNavOpen"
              >
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
              <nuxt-link
                v-for="(link, index) in links"
                :key="link.id"
                :to="{ path: link.path, hash: link.hash }"
                :class="{ 'mt-1': index !== 0 }"
                class="block px-3 py-2 rounded-md text-base font-medium text-gray-700 hover:text-gray-900 hover:bg-gray-50 focus:outline-none focus:text-gray-900 focus:bg-gray-50 transition duration-150 ease-in-out"
                role="menuitem"
                >{{ link.name }}</nuxt-link
              >
            </div>

            <div>
              <nuxt-link
                to="#contact"
                class="block w-full px-5 py-3 text-center font-medium text-indigo-600 bg-gray-50 hover:bg-gray-100 hover:text-indigo-700 focus:outline-none focus:bg-gray-100 focus:text-indigo-700 transition duration-150 ease-in-out"
                role="menuitem"
              >
                {{ cta }}
              </nuxt-link>
            </div>
          </div>
        </div>
      </div>
    </transition>
  </div>
</template>

<script>
export default {
  data() {
    return {
      links: [
        { name: 'Compétences', path: '/', hash: 'competences' },
        { name: 'Références', path: '/', hash: 'references' },
        { name: 'Réseaux', path: '/', hash: 'reseaux' },
        { name: 'Blog', path: '/', hash: 'blog' },
      ],
      cta: 'Contact',
      routeChange: false,
      mobileNavOpen: false,
    }
  },
  watch: {
    $route() {
      this.routeChange = true
      this.mobileNavOpen = false
    },
  },
  beforeMount() {
    window.addEventListener('scroll', this.handleScroll)
    window.addEventListener('touchmove', this.handleScroll)
  },
  beforeDestroy() {
    window.removeEventListener('scroll', this.handleScroll)
    window.removeEventListener('touchmove', this.handleScroll)
  },
  methods: {
    closeMobileNavbar() {
      this.mobileNavOpen = false
    },
    handleScroll() {
      // actions on scroll or touchmove events
      if (window.scrollY > 200) {
        this.closeMobileNavbar()
      }
    },
  },
}
</script>
