<template>
  <div class="bg-white">
    <div
      class="max-w-screen-xl mx-auto py-12 px-4 overflow-hidden sm:px-6 lg:px-8"
    >
      <!-- Navigation links -->
      <nav class="-mx-5 -my-2 flex flex-wrap justify-center">
        <nuxt-link
          v-for="link in links"
          :key="link.id"
          :to="{ path: link.path, hash: link.hash }"
          class="px-5 py-2 text-base leading-6 text-gray-500 hover:text-gray-900"
          >{{ link.name }}</nuxt-link
        >
      </nav>

      <!-- Social links -->
      <div id="reseaux" class="mt-8 flex justify-center">
        <p class="text-center text-base leading-6 text-gray-400">
          &copy; {{ actualYear }} Vincent REHM
        </p>

        <a
          target="_blank"
          class="ml-6"
          href="https://linkedin.com/in/vincentrehm/"
          data-tippy-content="@linkedin_handle"
        >
          <span class="sr-only">Linkedin</span>
          <svg
            class="h-6 fill-current text-gray-400 hover:text-gray-500"
            role="img"
            xmlns="http://www.w3.org/2000/svg"
            viewBox="0 0 24 24"
          >
            <title>Linkedin</title>
            <path
              d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.783 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z"
            /></svg
        ></a>

        <a
          target="_blank"
          class="ml-6"
          href="https://github.com/vrehm"
          data-tippy-content="@github_handle"
        >
          <span class="sr-only">Github</span>
          <svg
            class="h-6 fill-current text-gray-400 hover:text-gray-500"
            role="img"
            viewBox="0 0 24 24"
            xmlns="http://www.w3.org/2000/svg"
          >
            <title>GitHub</title>
            <path
              d="M12 .297c-6.63 0-12 5.373-12 12 0 5.303 3.438 9.8 8.205 11.385.6.113.82-.258.82-.577 0-.285-.01-1.04-.015-2.04-3.338.724-4.042-1.61-4.042-1.61C4.422 18.07 3.633 17.7 3.633 17.7c-1.087-.744.084-.729.084-.729 1.205.084 1.838 1.236 1.838 1.236 1.07 1.835 2.809 1.305 3.495.998.108-.776.417-1.305.76-1.605-2.665-.3-5.466-1.332-5.466-5.93 0-1.31.465-2.38 1.235-3.22-.135-.303-.54-1.523.105-3.176 0 0 1.005-.322 3.3 1.23.96-.267 1.98-.399 3-.405 1.02.006 2.04.138 3 .405 2.28-1.552 3.285-1.23 3.285-1.23.645 1.653.24 2.873.12 3.176.765.84 1.23 1.91 1.23 3.22 0 4.61-2.805 5.625-5.475 5.92.42.36.81 1.096.81 2.22 0 1.606-.015 2.896-.015 3.286 0 .315.21.69.825.57C20.565 22.092 24 17.592 24 12.297c0-6.627-5.373-12-12-12"
            /></svg
        ></a>
      </div>

      <!-- Propriété intellectuelle -->
      <div class="mt-8"></div>
    </div>
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
      routeChange: false,
      mobileNavOpen: false,
      actualYear: new Date().getFullYear(),
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
