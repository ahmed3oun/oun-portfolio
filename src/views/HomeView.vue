<script setup lang="ts">
import GPanel from '../components/GPanel.vue'
import photo from '@/assets/images/ahmed.jpg'
import {
  VsFileTypeAngular,
  VsFileTypeJsOfficial,
  VsFileTypeNode,
  VsFileTypeNestjs,
  VsFileTypePgsql,
  VsFileTypeTypescriptOfficial,
  VsFileTypeVue,
  AkLinkedInV2Fill,
  UnGithubAlt,
  SiCredly,
  DeDockerPlain ,
  DeTailwindcssPlain,
  DeMongodbOriginalWordmark 
} from '@kalimahapps/vue-icons'
import Star from '@/assets/images/star1.svg'

const user = {
  name: 'Ahmed Oun',
  profilePhoto: photo,
  occupation: 'Full-stack Developer',
  introduction: `I am a highly skilled full stack developer with a strong background in both frontend and backend technologies. I\'m specialized in Angular ,Vue 3 , NodeJS. I have a bachelor’s degree in computer science at 2019, engineer’s degree in web mobile development at 2022 and I’m OCA Java SE 8 certified from Oracle.`,
  slogan: [
    'NodeJs',
    'VueJs', 'Angular', 'Bootstrap5', 'Docker', 'Docker-compose', 'Nginx',
    'PostegreSQL', 'MongoDB', 'Websockets', 'Linux', 'Git', 'Vite',
    'HTML', 'CSS', 'SCSS', 'Javascript', 'Typescript', 'Java8', 'OOP', 'AWS'
  ]
}

const links = {
  credly: 'https://www.credly.com/users/ahmed-oun.b6d096a2/badges',
  github: 'https://github.com/ahmed3oun',
  linkedin: 'https://www.linkedin.com/in/ahmed-oun-1175a5147/'
}

const news = [
  '<span>Latest work and <strong>Featured</strong></span>',
  '<a href=`#`>Latest work and <strong>Featured</strong></a>',
  '<span>Latest work and <strong>Featured</strong></span>'
]

const stats = [
  {
    number: 1,
    title: 'Years Experience',
    prefix: '+'
  },
  {
    number: 25,
    title: 'Total Projects'
  }
]

const navigateTo = (link: string) => {
  switch (link) {
    case 'linkedin':
      const _window = window.open(links.linkedin, '_blank')
      _window.focus()
      break
    case 'github':
      const __window = window.open(links.github, '_blank')
      __window.focus()
      break
    case 'credly':
      const ___window = window.open(links.credly, '_blank')
      ___window.focus()
      break

    default:
      break
  }
}
</script>

<template>
  <main>
    <!-- Grid Pane -->
    <div class="grid grid-cols-2 sm:grid-cols-4 gap-6">
      <!-- User Info -->
      <GPanel to="#" span="4" :custom="true" class="intro-wrapper">
        <div class="bg-gray-200 rounded-tl-xl rounded-br-xl w-full h-full img-wrapper">
          <img class="rounded-tl-xl rounded-br-xl w-50 object-cover grayscale img-profile animate-pulse"
            :src="user.profilePhoto" alt="" />
        </div>
        <div class="flex flex-col gap-2 justify-center">
          <div class="uppercase text-sm">
            {{ user.occupation }}
          </div>
          <div class="text-4xl text-white font-semibold tracking-in-contract tracking-in-contract-bck-bottom">
            {{ user.name }}
          </div>
          <div>
            {{ user.introduction }}
          </div>
        </div>
      </GPanel>

      <!-- About User -->
      <div class="flex flex-col gap-6 col-span-2">
        <!-- Headlines Marquee -->
        <div>
          <div
            class="bg-gradient-to-r from-gray-800 to-gray-900 rounded-3xl flex flex-col justify-center px-4 py-3 border border-gray-800">
            <marquee behavior="" direction="">
              <div class="flex gap-2">
                <div v-for="(headline, i) in news" :key="i" class="flex">
                  <img class="mx-2" decoding="async" :src="Star" alt="*" />
                  <span v-html="headline"></span>
                </div>
              </div>
            </marquee>
          </div>
        </div>

        <div
          class="bg-gradient-to-r from-gray-800 to-gray-900 rounded-3xl flex flex-col justify-center px-4 py-3 border border-gray-800">
          <!-- Services -->
          <GPanel to="#" span="2" title="Technology Stack" subtitle="Specialization">
            <div class="h-12 flex justify-between items-center text-white">
              <!-- <LaLaravel class="text-5xl text-red-500" /> -->
              <VsFileTypeVue class="text-6xl text-[#41B883]" />
              <VsFileTypeAngular class="text-6xl text-cyan-400" />
              <DeTailwindcssPlain class="text-5xl text-[#07adca]" />
              <VsFileTypeTypescriptOfficial class="text-6xl" />
              <VsFileTypeJsOfficial class="text-6xl text-cyan-400" />
              <VsFileTypeNode class="text-6xl text-cyan-400" />
              <VsFileTypeNestjs class="text-6xl text-cyan-400" />
              <VsFileTypePgsql class="text-6xl text-cyan-400" />
              <DeMongodbOriginalWordmark  class="text-6xl text-cyan-400"/>
              <DeDockerPlain class="text-6xl text-cyan-400"/>
            </div>
          </GPanel>
          
        </div>
      </div>

      <!-- Social -->
      <GPanel span="2" to="#" title="Profiles" subtitle="Stay with Me">
        <div
          class="bg-gradient-to-br w-full from-gray-700 to-gray-900 border border-gray-700 rounded-3xl text-white flex items-center justify-between gap-2 p-2">
          <AkLinkedInV2Fill @click="navigateTo('linkedin')"
            class="text-6xl from-gray-700 to-gray-800 rounded-full p-2 hover:text-gray-700 hover:from-gray-100 hover:to-gray-300 shadow-md hover:shadow-none shadow-black transition-all" />
          <UnGithubAlt @click="navigateTo('github')"
            class="text-6xl from-gray-700 to-gray-800 rounded-full p-2 hover:text-gray-700 hover:from-gray-100 hover:to-gray-300 shadow-md hover:shadow-none shadow-black transition-all" />
          <SiCredly @click="navigateTo('credly')"
            class="text-6xl from-gray-700 to-gray-800 rounded-full p-2 hover:text-gray-700 hover:from-gray-100 hover:to-gray-300 shadow-md hover:shadow-none shadow-black transition-all" />
        </div>
      </GPanel>

      <!-- Stats -->
      <GPanel span="2">
        <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
          <div v-for="(stat, i) in stats" :key="i"
            class="flex flex-col justify-center items-center bg-gray-800 rounded-3xl gap-5 px-4 py-9">
            <div class="text-4xl text-white">
              <span v-if="stat.prefix!">
                {{ stat.prefix }}
              </span>
              <number class="bold transition" ref="number2" :from="0" :to="stat.number" :duration="5"
                easing="Power4.easeOut" />
            </div>
            <div class="uppercase text-sm text-center">
              {{ stat.title }}
            </div>
          </div>
        </div>
      </GPanel>

      <!-- CTA -->
      <GPanel to="#" custom span="2" sparkle class="items-end">
        <div>
          <div class="text-5xl text-white mb-2">
            Let's<br />
            work <span class="text-blue-600">together</span>.
          </div>
            <div class="flex flex-wrap">
              <span v-for="(_slogan, index) in user.slogan" :key="index"
                class="bg-gray-600 text-gray-100 text-xs font-medium mr-2 px-2.5 py-0.5 my-1 rounded-full dark:bg-gray-700 dark:text-gray-300">
                {{ _slogan }}
              </span>
            </div>
        </div>
      </GPanel>
    </div>
  </main>
</template>
<style>
.img-wrapper {
  max-height: 300px;
  height: auto;
  max-width: 300px;
  border-radius: 50%;
  overflow: hidden;
}

.img-profile {
  position: relative;
  top: -10%;
}

.scale-in-center {
  -webkit-animation: scale-in-center 0.5s cubic-bezier(0.25, 0.46, 0.45, 0.94) both;
  animation: scale-in-center 0.5s cubic-bezier(0.25, 0.46, 0.45, 0.94) both;
}

.tracking-in-contract {
  -webkit-animation: tracking-in-contract 0.8s cubic-bezier(0.215, 0.61, 0.355, 1) both;
  animation: tracking-in-contract 0.8s cubic-bezier(0.215, 0.61, 0.355, 1) both;
}

.animate-pulse {
  animation: pulse 2s cubic-bezier(0.4, 0, 0.6, 1) 2;
}

.tracking-in-contract-bck-bottom {
  -webkit-animation: tracking-in-contract-bck-bottom 1s cubic-bezier(0.215, 0.61, 0.355, 1) both;
  animation: tracking-in-contract-bck-bottom 1s cubic-bezier(0.215, 0.61, 0.355, 1) both;
}

@media (max-width: 935px) {
  .intro-wrapper {
    display: flex;
    flex-direction: column;
    padding-inline: auto;
  }

  .img-wrapper {
    margin-inline: auto;
    max-width: 250px;
  }
}
</style>
