<template>
    <main>
        <div class="grid grid-cols-1 sm:grid-cols-1 my-6 grid-wrapper">
            <GPanel class="w-full" span="4" title="Education">
                <ExperienceEducItem duration_date="Sep. 2016 – Aug. 2019" role="Bachelor’s degree in Computer Science"
                    company="Higher Institute of Information and Communication Technologies"
                    location="Ben arous, Borj cedria" />
                <ExperienceEducItem duration_date="Sep. 2019 – Oct. 2022" role="Web & mobile developement engineering"
                    company="TEK-UP private higher school of technologies & engineering" location="Tunis, Ariana" />
            </GPanel>
        </div>
        <div class="grid grid-cols-1 sm:grid-cols-1 gap-6 grid-wrapper">

            <GPanel class="flex flex-col w-full" span="1" title="Professional experience"
                subtitle="Click to show description" :sparkle="true">

                <ExperienceJobItem v-for="(item, index) in items" :class="{ 'active': (active_index === index) }"
                    :key="index" :company="item.company" :location="item.location" :duration_date="item.duration_date"
                    :role="item.role" :project="item.project" :technologies="item.technologies"
                    @click="showDescription(index)" />
            </GPanel>

            <VueFinalModal class="text-pop-up-top flex justify-center items-center"
                content-class=" text-pop-up-top flex flex-col max-w-xl mx-4 p-4 bg-white dark:bg-gray-900 border dark:border-gray-700 space-y-2 modal_wrapper"
                v-if="openDescriptionModal && (!Number.isNaN(active_index))" v-model="openDescriptionModal">
                <button class="modal__close" @click="toggleOpenDescModal()">
                    <CgClose />
                </button>
                <span class="modal__title">Experience Description</span>
                <p>
                    {{ items[active_index].description }}
                </p>
            </VueFinalModal>
            
        </div>
    </main>
</template>

<script setup lang="ts">
import GPanel from '@/components/GPanel.vue';
import { CgClose } from "@kalimahapps/vue-icons";
import ExperienceJobItem from "@/components/items/ExperienceJobItem.vue";
import ExperienceEducItem from "@/components/items/ExperienceEducItem.vue";
import { ref, type Ref } from "vue";
import { VueFinalModal } from 'vue-final-modal';

const active_index = ref(NaN);
const openDescriptionModal = ref(false)
const items: Ref<{
    company: string;
    location: string;
    duration_date: string;
    role: string;
    project: string;
    technologies: string[];
    description: string;
}[]> = ref([
    {
        company: 'Wolo',
        location: 'Tunis, North urban center',
        duration_date: 'Jan. 2024 - present',
        role: 'Fullstack Developer',
        project: 'Energy realtime monitoring dashboard, streamlining energy meters workflow and Admin manager Dashboard .',
        technologies: ['NestJS', 'Angular', 'Signals', 'Docker', 'Docker-compose', 'WSL', 'mongoDB', 'postgreSQL'],
        description: ` This mission started by developing an energy  realtime monitoring application, streamlining the renewable energy meters workflow.
        In addition it includes the ADMIN Manager dashboard that allow to manage all.
        `
    },
    {
        company: 'Tawa Digital Talents',
        location: 'Tunis, Lake 1',
        duration_date: 'Feb. 2022 - Jul. 2023',
        role: 'Fullstack Developer',
        project: 'Comprehensive social media analytics dashboard, streamlining influencer marketing workflow and Admin manager Dashboard .',
        technologies: ['NodeJS', 'VueJS', 'Vuex', 'Docker', 'Socket.io', 'mongoDB', 'postgreSQL'],
        description: ` This mission started by developing a matchmaking application to create a digital ecosystem to ensure
        the communication between influencers and advertisers, that offers to user discover new social media influencers according to its 
        needs, Consult their profile stats with flexible charts, Create advertising campaigns, Realtime communication with influencers.
        In addition we develop the ADMIN Manager dashboard that allow to admin manage all.
        `
    },
    {
        company: 'I CONNECT SERVICE',
        location: 'Tunis, Mannouba',
        duration_date: 'Jul. 2021 - Sep. 2021',
        role: 'Backend developer Trainee',
        project: 'Implements secured REST APIs with JWT and spring security.',
        technologies: ['Java8', 'Spring boot', 'Spring security', 'mongoDB', 'maven'],
        description: `This mission of 2 months, I developed a Spring boot server that allow to user to authenticate with multi role
        and upload/download files and manage their posts using spring security. 
        `

    },
    {
        company: 'I CONNECT SERVICE',
        location: 'Tunis, Mannouba',
        duration_date: 'Jul. 2020 - Sep. 2020',
        role: 'Mobile developer Trainee',
        project: 'Front-Flutter Development Treatment.',
        technologies: ['Flutter', 'Dart'],
        description: `It was a mission of 2 months, I started learning the basics of Dart language and Flutter.`

    },
    {
        company: 'XTEND',
        location: 'Tunis, North urban center',
        duration_date: 'Jan. 2019 - Apr. 2019',
        role: 'Developer Trainee',
        project: 'Web application that represents a social network telepresence system.',
        technologies: ['J2EE', 'Spring boot', 'Thymleaf', 'HTML', 'Javascript'],
        description: ``
    },
])

const showDescription = (index: number) => {
    active_index.value = index
    toggleOpenDescModal()
}

const toggleOpenDescModal = () => {
    openDescriptionModal.value ?
        openDescriptionModal.value = false :
        openDescriptionModal.value = true
} 
</script>

<style scoped>
.active {
    border-color: rgb(219, 219, 219);
}

.grid-wrapper {
    place-items: center;
}
</style>