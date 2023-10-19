<script setup lang="ts">
import { VueFinalModal } from 'vue-final-modal'

defineProps<{
    content?: string
}>()

const emit = defineEmits<{
    (e: 'exit'): void
}>()
</script>

<template>
    <VueFinalModal class="flex justify-center items-center"
        content-class="flex flex-col max-w-xl mx-4 p-4 bg-white dark:bg-gray-900 border dark:border-gray-700 rounded-xl space-y-2">
        <h1 class="text-xl">
            <slot />
            <!-- {{ content }} -->
        </h1>
        <button class="mt-1 ml-auto px-2 border rounded-lg" @click="emit('exit')">
            Exit
        </button>
    </VueFinalModal>
</template>

<style></style>