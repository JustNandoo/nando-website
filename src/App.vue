<template>
  <div class="max-w-7xl mx-auto flex flex-col relative">

    <!-- Navbar -->
    <nav class="max-w-7xl px-5 md:fixed top-0 z-[98] w-screen h-[80px] backdrop-blur-md bg-[#121212] bg-opacity-80 flex items-center">
      <div class="container mx-auto flex flex-wrap items-center justify-between">
        <button @click="redirectToHome" class="flex">
          <img :src="require('@/images/logo_nando.png')" alt="Logo Nando" class="w-32 h-32 object-contain">
        </button>
        <div class="flex md:order-2 fadein-bot space-x-4">
          <a href="https://github.com/JustNandoo" target="_blank">
            <img class="w-9 rounded-full" src="https://seeklogo.com/images/G/github-logo-2E3852456C-seeklogo.com.png" alt="GitHub">
          </a>
          <a href="https://www.instagram.com/justnandoo_/" target="_blank">
            <img class="w-9 rounded-full" src="https://upload.wikimedia.org/wikipedia/commons/a/a5/Instagram_icon.png" alt="Instagram">
          </a>
          <a href="https://www.linkedin.com/in/nando999/" target="_blank">
            <img class="w-9 rounded-full" src="https://upload.wikimedia.org/wikipedia/commons/c/ca/LinkedIn_logo_initials.png" alt="LinkedIn">
          </a>
        </div>
        <div class="hidden md:flex justify-between items-center w-full md:w-auto md:order-1">
          <ul class="flex-col md:flex-row flex md:space-x-8 mt-4 md:mt-0 md:text-sm md:font-medium">
            <li>
              <router-link to="/" class="nav-link">Home</router-link>
            </li>
            <li>
              <router-link to="/about" class="nav-link">About</router-link>
            </li>
            <li>
              <router-link to="/portfolio" class="nav-link">Portfolio</router-link>
            </li>
          </ul>
        </div>
      </div>
    </nav>

    <!-- Content -->
    <div class="md:mt-0 mb-4">
      <router-view />
    </div>

  </div>

  <!-- Footer -->
  <footer class="block md:hidden fixed bottom-0 left-0 right-0 rounded-t-3xl border border-[#383838] bg-[#121212] bg-opacity-80 backdrop-blur-md backdrop-opacity-90">
    <nav class="flex justify-around py-4 text-xs">
      <router-link to="/" class="text-gray-300 hover:text-white">Home</router-link>
      <router-link to="/about" class="text-gray-300 hover:text-white">About</router-link>
      <router-link to="/portfolio" class="text-gray-300 hover:text-white">Portfolio</router-link>
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
/* Styling umum */
body {
  font-family: 'Poppins', sans-serif;
  background: hsl(0, 0%, 7%);
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  height: 100vh;
  padding-top: 80px; /* Mencegah navbar menutupi konten */
}

/* Scrollbar kuning tetap ada */
::-webkit-scrollbar {
  width: 5px; /* Untuk scrollbar vertikal */
  height: 5px; /* Untuk scrollbar horizontal */
}

::-webkit-scrollbar-track {
  background: hsl(240, 1%, 17%);
  border-radius: 5px;
}

::-webkit-scrollbar-thumb {
  background: #ffdb70;
  border-radius: 5px;
}

::-webkit-scrollbar-button {
  width: 20px;
}
</style>
