<template>
    <div role="button"
        class="bg-gradient-to-br w-full from-gray-700 to-gray-900 border border-gray-700 rounded-3xl text-white flex flex-col gap-2 p-2">
        <div class="flex items-center justify-between w-full">
            <span class="text-white font-semibold m-1">
                {{ props.company }}
            </span>

            <span class="text-white font-semibold m-1">
                {{ props.location  }}
            </span>
        </div>
        <div v-if="props.role" class="flex items-center justify-between w-full">
            <span class="text-xs text-gray-400 font-semibold m-1">
                {{ props.role  }}
            </span>

            <span v-if="props.duration_date" class="text-xs  text-gray-400 font-semibold m-1">
                {{ props.duration_date  }}
            </span>
        </div>
        <span v-if="props.project" class="text-xs text-gray-400 font-semibold m-1">
            {{ props.project  }}
        </span>

        <span class="text-xs  text-gray-400 font-semibold m-1">

            <span v-if="props.technologies"
                class="bg-gray-600 text-white text-xs font-medium mr-2 px-2.5 py-0.5 my-1 rounded-full dark:bg-gray-700 dark:text-gray-300"
                v-for="(technology, index) in props.technologies" :key="index">
                {{ technology }}
            </span>
        </span>
    </div>
</template>

<script setup lang="ts">

const props = defineProps(["company", "role", "location", "duration_date", "technologies", "project"]);
</script>