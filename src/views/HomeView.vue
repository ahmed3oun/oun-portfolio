<script setup lang="ts">
import GPanel from '../components/GPanel.vue'
import photo from '@/assets/images/ahmed.jpg'
import { Twitter, Github } from 'iconoir-vue'
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
  SiCredly
} from '@kalimahapps/vue-icons'
import GFonts from '@/assets/images/gfonts.png'
import MyWorks from '@/assets/images/my-works.png'
import Sign from '@/assets/images/oun_signature.png'
import Star from '@/assets/images/star1.svg'
import { useRouter } from 'vue-router'

const router = useRouter()
const user = {
  name: 'Ahmed Oun',
  profilePhoto: photo,
  occupation: 'Full-stack Developer',
  introduction: `I am a highly skilled full stack developer with a strong background in both frontend and backend technologies. I\'m specialized in Angular ,Vue 3 , NodeJS. I have a bachelor’s degree in computer science at 2019, engineer’s degree in web mobile development at 2022 and I’m OCA Java SE 8 and OCI Oracle Cloud Infrastructure Foundations Associate certified from ORACLE.`,
  slogan:
    '#Nodejs #VueJS #Bootstrap5 #Redis #Websockets #MySQL #PostgreSQL #AWS #Serverless #Linux #Git #Docker #Nginx #JavaScript #TypeScript #HTML #CSS'
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
    number: 5,
    title: 'Years Experience',
    prefix: '+'
  },
  /* {
    number: 125,
    title: 'Clients Countrywide'
  }, */
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
      const ___window = window.open(links.credly,'_blank');
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
      <GPanel to="#" span="2" :custom="true">
        <div class="bg-gray-200 rounded-tl-xl rounded-br-xl w-full h-full">
          <img
            class="rounded-tl-xl rounded-br-xl w-50 h-full object-cover grayscale"
            :src="user.profilePhoto"
            alt=""
          />
        </div>
        <div class="flex flex-col gap-2 justify-center">
          <div class="uppercase text-sm">
            {{ user.occupation }}
          </div>
          <div class="text-4xl text-white font-semibold">
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
            class="bg-gradient-to-r from-gray-800 to-gray-900 rounded-3xl flex flex-col justify-center px-4 py-3 border border-gray-800"
          >
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

        <div class="grid grid-cols-4 sm:grid-cols-2 gap-6 w-full h-full">
          <!-- Services -->
          <GPanel to="#" span="2" title="Technology Stack" subtitle="Specialization">
            <div class="h-12 flex justify-between items-center text-white">
              <!-- <LaLaravel class="text-5xl text-red-500" /> -->
              <VsFileTypeVue class="text-6xl text-[#41B883]" />
              <VsFileTypeAngular class="text-6xl text-cyan-400" />
              <!-- <DeTailwindcssPlain class="text-5xl text-[#07adca]" /> -->
              <!-- <SiAlpinedotjs class="text-6xl text-cyan-400" /> -->
              <VsFileTypeTypescriptOfficial class="text-6xl" />
              <VsFileTypeJsOfficial class="text-6xl text-cyan-400" />
              <VsFileTypeNode class="text-6xl text-cyan-400" />
              <VsFileTypeNestjs class="text-6xl text-cyan-400" />
              <VsFileTypePgsql class="text-6xl text-cyan-400" />
              <VsFileTypeMongodb class="text-6xl text-cyan-400" />

              <!-- <SiLivewire class="text-5xl text-rose-400" /> -->
            </div>
          </GPanel>
          <!-- About -->
          <!-- <GPanel to="#" title="Credentials" subtitle="More About Me">
            <div>
              <img :src="Sign" alt="" />
            </div>
          </GPanel> -->

          <!-- Projects -->
          <!-- <GPanel to="#" title="Projects" subtitle="Showcase">
            <div>
              <img :src="MyWorks" alt="" />
            </div>
          </GPanel> -->
        </div>
      </div>

      <!-- Blog -->
      <!-- <GPanel to="#" title="Blog" subtitle="Useful Articles">
        <div>
          <img :src="GFonts" alt="" />
        </div>
      </GPanel> -->

      <!-- Social -->
      <GPanel span="2" to="#" title="Profiles" subtitle="Stay with Me">
        <div
          class="bg-gradient-to-br w-full from-gray-700 to-gray-900 border border-gray-700 rounded-3xl text-white flex items-center justify-between gap-2 p-2"
        >
          <AkLinkedInV2Fill
            @click="navigateTo('linkedin')"
            class="text-6xl from-gray-700 to-gray-800 rounded-full p-2 hover:text-gray-700 hover:from-gray-100 hover:to-gray-300 shadow-md hover:shadow-none shadow-black transition-all"
          />
          <UnGithubAlt
            @click="navigateTo('github')"
            class="text-6xl from-gray-700 to-gray-800 rounded-full p-2 hover:text-gray-700 hover:from-gray-100 hover:to-gray-300 shadow-md hover:shadow-none shadow-black transition-all"
          />
          <SiCredly
            @click="navigateTo('credly')"
            class="text-6xl from-gray-700 to-gray-800 rounded-full p-2 hover:text-gray-700 hover:from-gray-100 hover:to-gray-300 shadow-md hover:shadow-none shadow-black transition-all"
          />
          <!-- <UnGithubAlt      
            class="bg-gradient-to-br from-gray-700 to-gray-800 border border-gray-700 rounded-full p-6 hover:text-gray-700 hover:from-gray-100 hover:to-gray-300 shadow-md hover:shadow-none shadow-black transition-all"
          /> -->
          <!-- <Twitter
            class="bg-gradient-to-br from-gray-700 to-gray-900 border border-gray-700 rounded-full p-6 hover:text-gray-700 hover:from-gray-100 hover:to-gray-300 shadow-md hover:shadow-none shadow-black transition-all"
          /> -->
          <!-- <AiInspire
            class="bg-gradient-to-br from-gray-700 to-gray-900 border border-gray-700 rounded-full p-6 hover:text-gray-700 hover:from-gray-100 hover:to-gray-300 shadow-md hover:shadow-none shadow-black transition-all"
          /> -->
          <!-- <AkLinkedInV2Fill  
            class="bg-gradient-to-br from-gray-700 to-gray-900 border border-gray-700 rounded-full p-6 hover:text-gray-700 hover:from-gray-100 hover:to-gray-300 shadow-md hover:shadow-none shadow-black transition-all"
          /> -->
        </div>
      </GPanel>

      <!-- Stats -->
      <GPanel span="2">
        <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
          <div
            v-for="(stat, i) in stats"
            :key="i"
            class="flex flex-col justify-center items-center bg-gray-800 rounded-3xl gap-5 px-4 py-9"
          >
            <div class="text-4xl text-white">
              <span v-if="stat.prefix">
                {{ stat.prefix }}
              </span>
              <number
                class="bold transition"
                ref="number2"
                :from="0"
                :to="stat.number"
                :duration="5"
                easing="Power4.easeOut"
              />
            </div>
            <div class="uppercase text-sm text-center">
              {{ stat.title }}
            </div>
          </div>
        </div>
      </GPanel>

      <!-- CTA -->
      <GPanel to="#" custom span="4" sparkle class="items-end">
        <div>
          <div class="text-5xl text-white">
            Let's<br />
            work <span class="text-blue-600">together</span>.
          </div>
          <div class="text-xs text-zinc-500 mt-2">
            {{ user.slogan }}
          </div>
        </div>
      </GPanel>

      <!-- Notice -->
      <!--  <GPanel to="#" span="4" custom>
        <div class="text-sm">
          <p>
            I created this portfolio using <a href="#" class="text-[#41B883]">Vue3</a> and
            <a href="#" class="text-[#07adca]">TailwindCSS</a> for my own needs.<br />
            You are free to fork and use it as you may wish.<br />
            Most features are yet to be implemented, so any contributions will be nice.
          </p>
          <div class="mt-6">
            <a
              target="_blank"
              href="https://github.com/ahmed3oun"
              class="border border-gray-600 bg-gray-700 text-white px-6 py-3 rounded-xl hover:bg-white hover:text-gray-700 transition-all shadow-sm shadow-black"
            >
              View in Github
            </a>
          </div>
        </div>
      </GPanel> -->
    </div>
  </main>
</template>
