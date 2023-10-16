<template>
    <main>
        <div class="grid grid-cols-2 sm:grid-cols-2 gap-6 grid-wrapper">

            <GPanel class="flex flex-col w-full" span="1" :custom="true" title="Professional" subtitle="Experience"
                :sparkle="true">
                <ExperienceJobItem company="Tawa Digital Talents" location="Tunis, Lake 1"
                    duration_date="Feb. 2022 - Jul. 2023" role="Fullstack developer"
                    project="comprehensive social media analytics dashboard, streamlining influencer marketing workflow."
                    :technologies="['NodeJS', 'VueJS', 'Docker', 'Socket.io', 'mongoDB', 'postgreSQL']" />
                <ExperienceJobItem 
                    company="I CONNECT SERVICE" location="Tunis, Mannouba" duration_date="Jul. 2021 - Sep. 2021"
                    role="Backend developer Trainee" 
                    project="Implements secured REST APIs with JWT and spring security."
                    :technologies="['Java8', 'Spring boot', 'mongoDB', 'maven']"
                />
                <ExperienceJobItem 
                    company="I CONNECT SERVICE" location="Tunis, Mannouba" duration_date="Jul. 2020 - Sep. 2020"
                    role="Mobile developer Trainee" 
                    project="Front-Flutter Development Treatment."
                    :technologies="['Flutter', 'Dart']"
                />
                <ExperienceJobItem 
                company="XTEND" location="Tunis, North urban center" duration_date="Jan. 2019 - Apr. 2019"
                    role="Developer Trainee" 
                    project="Web application that presents a social network telepresence system."
                    :technologies="['J2EE', 'Spring boot', 'Thymleaf', 'HTML', 'Javascript']"
                />
                <ExperienceJobItem />
            </GPanel>

            <GPanel class="flex flex-col" span="1" subtitle="Job Description">
                <div class="text-3xl text-neutral-500 mb-5">
                    Description
                </div>
                <div class="text-neutral-300">
                    <span>
                        Lorem ipsum dolor sit, amet consectetur adipisicing elit. Animi provident saepe voluptatibus?
                        Tempore laborum vitae praesentium deserunt libero, error maiores aperiam assumenda, perspiciatis
                        molestias atque esse, provident temporibus alias recusandae.
                        .<br />
                        Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptatibus accusamus eligendi
                        necessitatibus tenetur, ratione numquam quisquam perferendis odio iusto velit recusandae odit
                        suscipit corrupti.<br />
                        Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dolorum officiis cum quas dolorem eligendi
                        nam aut ipsa.<br />
                    </span>
                </div>
            </GPanel>
        </div>
    </main>
</template>

<script setup lang="ts">
import GPanel from '@/components/GPanel.vue';
import ExperienceJobItem from "@/components/items/ExperienceJobItem.vue";


</script>

<style scoped>
.grid-wrapper {
    place-items: center;
}
</style>