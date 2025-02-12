<template>
  <!-- component -->
  <!-- This is an example component -->
  <div class="max-w-7xl mx-auto flex flex-col relative">

    <nav class="max-w-7xl px-5 md:fixed top-0 z-[98] w-screen backdrop-blur-md bg-[#121212] bg-opacity-80">
      <div class="container mx-auto flex flex-wrap items-center justify-between">
        <button @click="redirectToHome" class="flex">
          <span class="self-center text-lg text-[#ffdb70] font-semibold whitespace-nowrap fadein-bot hover:text-amber-100">Ferdiansyah Wurtami();</span>
        </button>
        <div class="flex md:order-2 fadein-bot">
          <a href="https://github.com/brxzzyall"><img class="w-9 rounded-full" src="data:image/png;base64,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" alt="github"></a>
        </div>
        <div class="hidden md:flex justify-between items-center w-full md:w-auto md:order-1" id="mobile-menu-3">
          <ul class="flex-col md:flex-row flex md:space-x-8 mt-4 md:mt-0 md:text-sm md:font-medium">
            <li>
              <router-link to="/"
                class="fadein-bot text-gray-700 hover:bg-gray-50 border-b border-gray-100 md:hover:bg-transparent md:border-0 block pl-3 pr-4 py-2 md:hover:text-gray-500 md:p-0"
                aria-current="page">Home</router-link>
            </li>
            <li>
              <router-link to="/about"
                class="fadein-bot fadein-1 text-gray-700 hover:bg-gray-50 border-b border-gray-100 md:hover:bg-transparent md:border-0 block pl-3 pr-4 py-2 md:hover:text-gray-500 md:p-0">About</router-link>
            </li>
            <li>
              <router-link to="/portfolio"
                class="fadein-bot fadein-2 text-gray-700 hover:bg-gray-50 border-b border-gray-100 md:hover:bg-transparent md:border-0 block pl-3 pr-4 py-2 md:hover:text-gray-500 md:p-0">Portfolio</router-link>
            </li>
            <li>
              <router-link to="/blog"
                class="fadein-bot fadein-3 text-gray-700 hover:bg-gray-50 border-b border-gray-100 md:hover:bg-transparent md:border-0 block pl-3 pr-4 py-2 md:hover:text-gray-500 md:p-0 blog">Blog</router-link>
            </li>
          </ul>
        </div>
      </div>
    </nav>

    <div class="md:mt-[100px]">
      <router-view />
    </div>
  </div>
  <footer class="block md:hidden fixed bottom-0 left-0 right-0 rounded-t-3xl border border-[#383838] bg-[#121212] bg-opacity-80 backdrop-blur-md backdrop-opacity-90">
  <nav class="flex justify-around py-4 text-xs">
    <router-link to="/" class="text-gray-300 hover:text-white">Home</router-link>
    <router-link to="/about" class="text-gray-300 hover:text-white">About</router-link>
    <router-link to="/portfolio" class="text-gray-300 hover:text-white">Portfolio</router-link>
    <router-link to="/blog" class="text-gray-300 hover:text-white">Blog</router-link>
  </nav>
</footer>
</template>

<script>
export default {
  methods: {
    redirectToHome() {
      this.$router.push('/')
    }
  },
}
</script>

<style>
*,
*::before,
*::after {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

::-webkit-scrollbar {
  width: 5px; /* for vertical scrollbar */
  height: 5px; /* for horizontal scrollbar */
}

::-webkit-scrollbar-track {
  background: hsl(240, 1%, 17%);
  border-radius: 5px;
}

::-webkit-scrollbar-thumb {
  background: #ffdb70;
  border-radius: 5px;
}

::-webkit-scrollbar-button { width: 20px; }

body {
  font-family: 'Poppins', sans-serif;
  background: hsl(0, 0%, 7%);
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  height: 100vh;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
  transition: color 0.3s;
}

nav a.router-link-exact-active {
  display: inline-flex;
  flex-direction: column;
  color: white;
  transition: color 0.3s;
}

nav a.router-link-exact-active::after {
  display: inline-block;
  content: "";
  margin-top: 0.08em;
  width: 100%;
  height: 4px;
  border-radius: 2px;
  background-color: #ffdb70;
}

nav a.router-link-exact-active:hover {
  color: white;
}


@keyframes fadeInLeft {
  0% {
    opacity: 0;
    transform: translateX(-100%);
  }
  100% {
    opacity: 1;
    transform: translateX(0);
  }
}

</style>
