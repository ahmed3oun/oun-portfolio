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
                    <div class="text-3xl text-neutral-500 w-fit mb-5">
                        About me
                    </div>
                    <div class="text-5xl mb-2 w-fit">
                        <h1 class="type">Hello, I'm Ahmed</h1>
                    </div>
                    <div class="text-neutral-300 mb-2">
                        <p class="zoom-out">
                            I am a <span class="text-[#ab999a]">fullstack Javascript/Typescript developer</span> based
                            in Tunisia,
                            I love communication with others, writing clean code and pushing my skills to the limit with
                            <span class="text-[#ab999a]">a good knowledge in backends best practices</span>
                            and <span class="text-[#ab999a]">skilled in frontend development</span>
                            .<br />
                            I have been working with javascript for more than <span class="text-[#ab999a]">5
                                years</span> now and I love it!.<br />
                            I have been working with <span class="text-[#ab999a]">NodeJS, NestJS, Angular, VueJS and
                                React</span>
                            for the last <span class="text-[#ab999a]">2 years</span> and nowadays I am comfortable with
                            the fullstack JS.<br />
                            <br />
                            <span>On the other hand, I also have a <span class="text-[#ab999a]">DevOps background</span>.
                             I’m comfortable working in <span class="text-[#ab999a]">Linux</span> environments,
                              particularly <span class="text-[#ab999a]">Ubuntu</span> through <span class="text-[#ab999a]">WSL</span></span>.<br/>
                            <span>I have good knowledge of <span class="text-[#ab999a]">Docker</span> and experience in creating
                               application infrastructures using <span class="text-[#ab999a]">Docker Compose</span>.
                               I also have some hands-on experience with <span class="text-[#ab999a]">Kubernetes</span>
                                and building <span class="text-[#ab999a]">CI/CD</span> pipelines using
                                <span class="text-[#ab999a]">GitLab CI/CD</span> for deployment.</span><br/>
                            
                            <span>Additionally, I’m an <span class="text-[#ab999a]">AWS Practitioner</span> 
                                with experience in services like <span class="text-[#ab999a]">EC2, S3 and EKS.</span> </span><br/>
                            <br />
                            My interests include joining an exciting team of passionate people, personal
                            growth, make new contacts to improve my communication skills.<br />
                            <br />
                            About my strenghths, I'm a <span class="text-[#ab999a]">good team player</span>, collaborative and always,
                            I share my knowledge with others, In addition I'm <span class="text-[#ab999a]">autonomous</span> and <span class="text-[#ab999a]">creative</span>.<br />
                            About my weakness,
                            I'm <span class="text-[#ab999a]">perfectionist</span> I take little more time to give a nice feature
                            and I concentrate more with little details.<br />
                        </p>
                    </div>
                    <!-- <button @click="downloadPdf()"
                        class="bg-gray-300 hover:bg-gray-400 text-gray-800 font-bold py-2 my-2 px-4 rounded inline-flex items-center">
                        <svg class="fill-current w-4 h-4 mr-2" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20">
                            <path d="M13 8V2H7v6H2l8 8 8-8h-5zM0 18h20v2H0v-2z" />
                        </svg>
                        <span>View resume</span>
                    </button> -->
                </div>
            </GPanel>
        </div>
    </main>
</template>

<script setup lang="ts">
import pdfResume from "@/assets/Ahmed_OUN_Resume.pdf";
import GPanel from '@/components/GPanel.vue';
import photo from '@/assets/images/ahmed.jpg'

const user = {
    name: 'Ahmed Oun',
    profilePhoto: photo,
    occupation: 'Full-stack Developer',
    introduction: `I am a highly skilled full stack developer with a strong background in both frontend and backend technologies. I\'m specialized in Angular ,Vue 3 , NodeJS. I have a bachelor’s degree in computer science at 2019, engineer’s degree in web mobile development at 2022 and I’m OCA Java SE 8.`,
}

const downloadPdf = () => {
    const blob = new Blob([pdfResume], { type: 'application/pdf' })
    const url = URL.createObjectURL(blob)
    const link = document.createElement('a')
    link.href = url
    link.download = 'Ahmed_OUN_Resume.pdf'
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

.intro-wrapper {
    display: flex;
    flex-direction: column;
    padding-inline: auto;
}

.img-wrapper {
    border-radius: 29% 71% 67% 33% / 22% 30% 70% 78%;
    max-height: 500px;
    height: auto;
    max-width: 500px;
    overflow: hidden;
    margin-inline: auto;
    max-width: 250px;
    animation: zoom-in-zoom-out 1.5s linear 1;
}

.img-profile {
    width: auto;
}

.zoom-out {
    animation: zoom-out 2s normal 1;
}

@keyframes zoom-in-zoom-out {
    0% {
        scale: 100%;
    }

    50% {
        scale: 150%;
    }

    100% {
        scale: 100%;
    }
}

@keyframes zoom-out {
    0% {
        scale: 130%;
    }

    100% {
        scale: 100%;
    }
}



/* Custom */

h1 {
    background: -webkit-linear-gradient(25deg, #eee, #1f1f1f);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    font-size: 3rem;
    font-weight: 500;
    overflow: hidden;
    white-space: nowrap;
    border-right: 2px solid;
    animation: type 1.5s steps(90) 1.5s 1 normal both, cursor 1s step-end infinite;
    position: relative;
}

@keyframes type {
    from {
        width: 0;
    }

    to {
        width: 100%;
    }
}

@keyframes cursor {
    50% {
        border-color: transparent;
    }
}
</style>