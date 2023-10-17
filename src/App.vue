<script setup lang="ts">
import { RouterLink, RouterView, useRoute } from 'vue-router'
import Logo from '@/assets/images/white-oun-logo-wt-bg.png'

const route = useRoute()
</script>

<template>
  <div class="sm:max-w-6xl sm:mx-auto text-gray-500 py-5 transition-all">
    <!-- Header -->
    <div id="header" class="flex w-full justify-between px-2 sm:p-2">
      <!-- Logo -->
      <div id="logo">
        <img class="h-10" :src="Logo" alt="" />
      </div>
      <!-- Nav -->
      <div id="nav-menu" class="hidden sm:flex gap-10">
        <div :class="{'text-white' : route.path === '/'}">
          <RouterLink to="/">Home</RouterLink>
        </div>
        <div :class="{'text-white' : route.path === '/about'}">
          <RouterLink to="/about">About</RouterLink>
        </div>
        <div :class="{'text-white' : route.path === '/works'}" >
          <RouterLink to="/works">Works</RouterLink>
        </div>
        <!-- <div>
          <RouterLink to="/about">Contact</RouterLink>
        </div> -->
      </div>
      <!-- CTA Button -->
      <div id="cta-btn">
        <a
          href="mailto:ahmedoun199@gmail.com"
          class="bg-gray-700 text-white px-6 py-3 rounded-xl hover:bg-white hover:text-gray-700 transition-all"
        >
          Let's Talk
        </a>
      </div>
    </div>
    <!-- Router view -->
    <div class="my-10 sm:my-20 px-4 xl:p-0">
      <RouterView />
    </div>
    <!-- Footer -->
    <div class="flex flex-col items-center gap-8">
      <!-- Logo -->
      <div id="logo">
        <img class="h-12" :src="Logo" alt="" />
      </div>
      <!-- Nav -->
      <div id="nav-menu" class="flex gap-10">
        <div :class="{'text-white' : route.path === '/'}">
          <RouterLink to="/">Home</RouterLink>
        </div>
        <div :class="{'text-white' : route.path === '/about'}" >
          <RouterLink to="/about">About</RouterLink>
        </div>
        <div :class="{'text-white' : route.path === '/works'}" >
          <RouterLink to="/works">Works</RouterLink>
        </div>
      </div>
      <!-- Copyright -->
      <div class="text-gray-500">
        © {{ new Date().getFullYear() }} <a href="#" class="text-blue-500">Oun</a>. All rights
        reserved.
      </div>
    </div>
  </div>
</template>

<style>
*::-webkit-scrollbar {
  width: 10px;
}

/* Track */
*::-webkit-scrollbar-track {
  background: #d8d7d7ad; 
}
 
/* Handle */
*::-webkit-scrollbar-thumb {
  background: linear-gradient(#464646f6,#838383f6,#464646f6); 
  border-radius: 12px;
}

/* Handle on hover */
*::-webkit-scrollbar-thumb:hover {
  background: #2b2b2b; 
}
</style>
