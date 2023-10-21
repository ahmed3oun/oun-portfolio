<template>
    <main>
        <div class="grid grid-cols-2 sm:grid-cols-2 gap-6 grid-wrapper">
            <!-- BEGIN Left side -->
            <GPanel span="1" :custom="true" class="to-trans" subtitle="Who am i ?" :sparkle="true">
                <div class="flex-col">
                    <div class=" rounded-tl-xl rounded-br-xl w-full h-full img-wrapper">
                        <img class="rounded-tl-xl rounded-br-xl w-50 object-cover  img-profile animate-rotate"
                            :src="user.profilePhoto" alt="" />
                    </div>
                </div>

            </GPanel>
            <!-- END Right Side -->
            <GPanel span="1" :custom="true" class="to-trans" subtitle="Who am i ?" :sparkle="true">
                <div class="flex-col">
                    <div class="text-3xl text-neutral-500 mb-5">
                        About me
                    </div>
                    <div class="text-5xl text-white mb-2">
                        Hello, I'm <span class="text-blue-600">Ahmed!</span>
                    </div>
                    <div class="text-neutral-300">
                        <span>
                            I am a fullstack Javascript/Typescript developer based in Tunisia,
                            I love communication with others, writing clean code and pushing my skills to the limit with a
                            good knowledge in backends best practices and skilled in frontend development
                            .<br />
                            I have been working with javascript for more than 4 years now and I love it!.<br />
                            I have been working with NodeJS and VueJS for the last 2 years and nowadays I am comfortable
                            with the fullstack JS.<br />
                        </span>
                        <br />
                        <span>
                            My interests include joining an exciting team of passionate people, personal
                            growth, make new contacts to improve my communication skills.<br />
                        </span>
                        <br />
                        <span>
                            About my strenghths, I'm collaborative and always,
                            I share my knowledge with others, In addition I'm autonomous and creative.<br />
                            About my weakness
                            Maybe im perfectionist I take little more time to give a nice feature
                            and I concentrate more with little details.<br />
                        </span>
                    </div>
                    <button @click="downloadPdf()"
                        class="bg-gray-300 hover:bg-gray-400 text-gray-800 font-bold py-2 my-2 px-4 rounded inline-flex items-center">
                        <svg class="fill-current w-4 h-4 mr-2" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20">
                            <path d="M13 8V2H7v6H2l8 8 8-8h-5zM0 18h20v2H0v-2z" />
                        </svg>
                        <span>View resume</span>
                    </button>
                </div>
            </GPanel>
        </div>
    </main>
</template>

<script setup lang="ts">
import resume from "@/assets/Ahmed_OUN_Resume.pdf";
import GPanel from '@/components/GPanel.vue';
import photo from '@/assets/images/ahmed.jpg'

const user = {
    name: 'Ahmed Oun',
    profilePhoto: photo,
    occupation: 'Full-stack Developer',
    introduction: `I am a highly skilled full stack developer with a strong background in both frontend and backend technologies. I\'m specialized in Angular ,Vue 3 , NodeJS. I have a bachelor’s degree in computer science at 2019, engineer’s degree in web mobile development at 2022 and I’m OCA Java SE 8.`,
    slogan:
        '#Nodejs #VueJS #Bootstrap5 #Redis #Websockets #MySQL #PostgreSQL #AWS #Serverless #Linux #Git #Docker #Nginx #JavaScript #TypeScript #HTML #CSS'
}

// how to center a div with grid display ?

const downloadPdf = () => {
    const blob = new Blob([resume], { type: 'application/pdf' })
    const url = URL.createObjectURL(blob)
    const link = document.createElement('a')
    link.href = url
    link.download = 'Ahmed_oun_resume.pdf'
    link.click()
    URL.revokeObjectURL(url)
}
</script>

<style scoped>
.to-trans {
    --tw-gradient-to: auto;
    border: none;
}

.grid-wrapper {
    place-items: center;
}

.img-wrapper {
    border-radius: 29% 71% 67% 33% / 22% 30% 70% 78%;
    max-height: 500px;
    height: auto;
    max-width: 500px;

    overflow: hidden;
}

.intro-wrapper {
    display: flex;
    flex-direction: column;
    padding-inline: auto;
}

.img-wrapper {
    margin-inline: auto;
    max-width: 250px;
}

.img-profile {
    animation: rotate 1s linear 1;
}

@keyframes rotate {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}
</style>