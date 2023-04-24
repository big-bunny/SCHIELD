<template>
<header id="home" class=" fixed container flex justify-around items-center py-1">
  <nav id="Home" class="flex items-center rounded  justify-between  border rounded-40 border-red-600 flex-wrap bg-gray-800 p-6">
    <div class="flex items-center flex-shrink-0 text-white mr-6">
      <img class="h-8 w-8" :src="$config.schoolLogo" alt="Logo">
      <span class="font-semibold text-xl tracking-tight ml-2">SCHIELD CENTER</span>
    </div>
    <div class="block lg:hidden">
      <button
        class="flexitems-center px-3 py-2 border rounded text-gray-500 border-gray-500 hover:text-white hover:border-white"
        @click="isMenuOpen = !isMenuOpen"
      >
        <svg
          class="fill-current h-3 w-3"
          viewBox="0 0 20 20"
          xmlns="http://www.w3.org/2000/svg"
        >
          <title>Menu</title>
          <path
            :class="[isMenuOpen ? 'hidden' : '']"
            d="M0 3h20v2H0V3zm0 6h20v2H0V9zm0 6h20v2H0v-2z"
          />
          <path
            :class="[isMenuOpen ? '' : 'hidden']"
            d="M0 3h20v2H0V3zm0 8h20v2H0v-2zm0 8h20v2H0v-2z"
          />
        </svg>
      </button>
    </div>
    <div :class="[isMenuOpen ? 'block' : 'hidden', 'w-full block flex-grow lg:flex lg:items-center lg:w-auto']">
      <div class="text-lg text-black-500 lg:flex-grow">
        <a href="#about" class="block lg:inline-block  text-xl hover:text-black mr-4 text-black md: block text-primary text-center px-6 py-2 rounded-full mr-2 hover:bg-accent">
          ABOUT-SCHIELD
        </a>
        <a href="#news" class="block lg:inline-block  hover:text-black mr-4 text-black md: block text-primary text-center px-6 py-2 rounded-full mr-2 hover:bg-accent">
          BLOG
        </a>
        <!-- dropdown -->
        <div class="inline-block relative mt-4 lg:mt-0 text-black-500 block lg:inline-block  hover:text-red mr-4 md: block px-4 py-2 text-primary text-center  rounded mr-2 hover:bg-accent">
          <a href="#"  class="block lg:inline-block text-xl hover:text-black mr-4 text-black md: block  lg:inline-block text-primary text-center px-6 py-2 rounded-full mr-2 hover:bg-accent">
            SPONSOR
          </a>
          <div class="dropdown absolute hidden bg-gray-800 text-black py-2 rounded-lg z-10">
            <a href="#child" class="block  text-black-500 hover:text-green mr-4 md: block  text-primary text-center px-6 py-2 rounded-full mr-2 hover:bg-accent">Support a child</a>
            <a href="#programs" class="block text-black-500 hover:text-green mr-4 md: block  text-primary text-center px-6 py-2 rounded-full mr-2 hover:bg-accent">Sponsor a program</a>
          </div>
        </div>
        <a href="#mission-vision" class="block lg:inline-block text-black-500 hover:text-black mr-4 md: block text-primary text-center px-6 py-2 rounded-full mr-2 hover:bg-accent">
          MISSION-VISSION
        </a>
        <a href="#staff" class="block lg:inline-block text-black-500 hover:text-black mr-4 md: block  text-primary text-center px-6 py-2 rounded-full mr-2 hover:bg-accent">
          OUR-TEAM
        </a>
        <a href="#gallery" class="block lg:inline-block text-black-500 hover:text-black mr-4 md: block text-primary text-center px-6 py-2 rounded-full mr-2 hover:bg-accent">
          GALLERY
        </a>
        <a href="#contact" class="block lg:inline-block text-black-500 hover:text-black mr-4 md: block text-primary text-center px-6 py-2 rounded-full mr-2 hover:bg-accent">
          CONTACT-US
  </a>
  
</div>
<div class="relative" x-data="{ isOpen: false }" @click.away="isOpen = false">
    <button @click="isOpen = !isOpen" class="block lg:inline-block flex items-center justify-center w-12 h-12 rounded-full bg-gray-200 hover:bg-gray-300 focus:outline-none focus:shadow-outline-gray" aria-label="Profile">
      <i class="fas fa-user text-gray-800"></i>  
    </button>
    <!-- <div  class="absolute right-0 mt-2 py-2 w-48 bg-white rounded-md shadow-lg z-10"> -->
      <div id="login"  x-show="isOpen" class="login-container px-4 py-2">
        <partials-login />
        <!-- <partials-signup/> -->
      <!-- </div> -->
    </div>
  </div>
  
    </div>
  </nav></header>
</template>

<script lang="ts">
import { defineComponent } from 'vue';


export default defineComponent({
  data() {
    return {
      isMenuOpen: false,
    };
  },
});
</script>

<style scoped>

.inline-block:hover .dropdown {
  display: block;
}




.dropdown > .dropdown > a:hover {
  background-color: #15d468;
}


@media (min-width: 640px) {
  .navbar-menu {
    display: flex !important;
    flex-grow: 1;
    justify-content: flex-end;
  }
  .inline-block:hover .dropdown {
  display: block;
}




.dropdown > .dropdown > a:hover {
  background-color: #15d468;
}

}
</style>
