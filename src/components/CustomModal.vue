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
    <VueFinalModal
        class="flex align-center items-center flex-col max-w-xl mx-4 p-4 bg-gray-600 border dark:border-gray-700 rounded-lg space-y-2">
        <h1 class="text-xl">
            {{ content }}
        </h1>
        <slot />
        <button class="mt-1 ml-auto px-2 border rounded-lg" @click="emit('exit')">
            Exit
        </button>
    </VueFinalModal>
</template>