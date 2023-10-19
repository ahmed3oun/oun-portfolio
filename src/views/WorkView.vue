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

            <!-- <VueFinalModal class="flex justify-center items-center"
                content-class="flex flex-col max-w-xl mx-4 p-4 bg--700 dark:bg-gray-900 border dark:border-gray-700 rounded-lg space-y-2"
                v-if="openDescriptionModal" v-model="openDescriptionModal"> -->
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
            <!-- <GPanel class="flex flex-col" span="1" subtitle="Job Description">
                <div class="text-3xl text-neutral-500 mb-5">
                    Description
                </div>
                <div class="text-neutral-300">
                    <span v-if="!Number.isNaN(active_index)">
                        {{ items[active_index].description }}
                    </span>
                    <span v-else>
                        No description
                    </span>
                    <span>
                        {{ active_index }}
                    </span>
                </div>
            </GPanel> -->
        </div>
    </main>
</template>

<script setup lang="ts">
import GPanel from '@/components/GPanel.vue';
import { CgClose } from "@kalimahapps/vue-icons";
/* import { ModalsContainer, useModal } from 'vue-final-modal' */
import ExperienceJobItem from "@/components/items/ExperienceJobItem.vue";
import ExperienceEducItem from "@/components/items/ExperienceEducItem.vue";
import { ref, watch, type Ref } from "vue";
import { VueFinalModal } from 'vue-final-modal';
//import CustomModal from '@/components/CustomModal.vue';

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
        company: 'Tawa Digital Talents',
        location: 'Tunis, Lake 1',
        duration_date: 'Feb. 2022 - Jul. 2023',
        role: 'Fullstack Developer',
        project: 'Comprehensive social media analytics dashboard, streamlining influencer marketing workflow and Admin manager Dashboard .',
        technologies: ['NodeJS', 'VueJS', 'Docker', 'Socket.io', 'mongoDB', 'postgreSQL'],
        description: ` This mission started by developing a matchmaking application to create a digital ecosystem to ensure
        the communication between influencers and advertisers, that offers to user discover new social media influencers according to its 
        needs, Consult their profile stat charts  
        `
    },
    {
        company: 'I CONNECT SERVICE',
        location: 'Tunis, Mannouba',
        duration_date: 'Jul. 2021 - Sep. 2021',
        role: 'Backend developer Trainee',
        project: 'Implements secured REST APIs with JWT and spring security.',
        technologies: ['Java8', 'Spring boot', 'Spring security', 'mongoDB', 'maven'],
        description: `Lorem ipsum dolor sit amet consectetur adipisicing elit. Perspiciatis tempora cum saepe ea labore adipisci nemo, error odio dolorum, ipsa dicta dolorem obcaecati magni nihil reiciendis velit nesciunt voluptatem? Provident!`

    },
    {
        company: 'I CONNECT SERVICE',
        location: 'Tunis, Mannouba',
        duration_date: 'Jul. 2020 - Sep. 2020',
        role: 'Mobile developer Trainee',
        project: 'Front-Flutter Development Treatment.',
        technologies: ['Flutter', 'Dart'],
        description: `Lorem ipsum dolor sit amet consectetur adipisicing elit. Perspiciatis tempora cum saepe ea labore adipisci nemo, error odio dolorum, ipsa dicta dolorem obcaecati magni nihil reiciendis velit nesciunt voluptatem? Provident!`

    },
    {
        company: 'XTEND',
        location: 'Tunis, North urban center',
        duration_date: 'Jan. 2019 - Apr. 2019',
        role: 'Developer Trainee',
        project: 'Web application that represents a social network telepresence system.',
        technologies: ['J2EE', 'Spring boot', 'Thymleaf', 'HTML', 'Javascript'],
        description: `Lorem ipsum dolor sit amet consectetur adipisicing elit. Perspiciatis tempora cum saepe ea labore adipisci nemo, error odio dolorum, ipsa dicta dolorem obcaecati magni nihil reiciendis velit nesciunt voluptatem? Provident!`
    },
])

watch(() => active_index, (newValue, oldValue) => {
})

/* const { open, close } = useModal({
    component: CustomModal,
    attrs: {
        content: items.value[active_index.value]?.description,
        onExit() {
            close()
        },
    },
    slots: {
        default: `<p>${items.value[active_index.value]?.description || 'TEST'}</p>`,
    },
}) */

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