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
        <div :class="{ 'text-white': route.path === '/' }">
          <RouterLink to="/">Home</RouterLink>
        </div>
        <div :class="{ 'text-white': route.path === '/about' }">
          <RouterLink to="/about">About</RouterLink>
        </div>
        <div :class="{ 'text-white': route.path === '/works' }">
          <RouterLink to="/works">Works</RouterLink>
        </div>
        <!-- <div>
          <RouterLink to="/about">Contact</RouterLink>
        </div> -->
      </div>
      <!-- CTA Button -->
      <div id="cta-btn">
        <a href="mailto:ahmedoun199@gmail.com"
          class="bg-gray-700 text-white px-6 py-3 rounded-xl hover:bg-white hover:text-gray-700 transition-all">
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
        <div :class="{ 'text-white': route.path === '/' }">
          <RouterLink to="/">Home</RouterLink>
        </div>
        <div :class="{ 'text-white': route.path === '/about' }">
          <RouterLink to="/about">About</RouterLink>
        </div>
        <div :class="{ 'text-white': route.path === '/works' }">
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

.text-pop-up-top {
  -webkit-animation: text-pop-up-top 0.5s cubic-bezier(0.250, 0.460, 0.450, 0.940) both;
  animation: text-pop-up-top 0.5s cubic-bezier(0.250, 0.460, 0.450, 0.940) both;
}

.modal_wrapper {
  border-radius: 1rem;
  font-family: Inter;
  overflow: auto;
}

.modal_wrapper .modal__close {
  align-self: flex-end;
  padding: 0.5rem;
  border-radius: 50%;
  border-color: rgb(0, 0, 0);
  box-shadow: rgba(0, 0, 0, 0.35) 0px 5px 15px;
}
.modal_wrapper .modal__close:hover {
  background-color: #5f5f5f;
  color: white;
}

.modal_wrapper .modal__title {
  font-weight: bold;
}

*::-webkit-scrollbar {
  width: 8.75px;
}

/* Track */
*::-webkit-scrollbar-track {
  background: #e0e0e0ad;
  border-radius: 10px;
}

/* Handle */
*::-webkit-scrollbar-thumb {
  background: linear-gradient(#464646f6, #585858f6, #353535f6);
  border-radius: 10px;
}

/* Handle on hover */
*::-webkit-scrollbar-thumb:hover {
  background: #2b2b2b;
}
</style>
