<template>
    <div class="flex flex-row items-center max-w-xs">
        <img 
            class="mb-4" 
            :width="imageSize.width" 
            :height="imageSize.height" 
            src="/images/logo/logo.png" 
            alt="Logo" 
        />
        <div 
            :class="['font-bold font-mplus-rounded mb-4', textSizeClass, props.darkMode !== undefined ? props.darkMode ? 'text-black' : 'text-white' : 'dark:text-white text-black']"
        >
            Vita
        </div>
    </div>
</template>

<script setup lang="ts">
import { computed } from 'vue'

const props = withDefaults(defineProps<{
    size?: 'extra-small' | 'small' | 'medium' | 'large'
    darkMode?: boolean
}>(), {
    size: 'large',
})

const imageSize = computed(() => {
    switch (props.size) {
        case 'extra-small':
            return { width: 50, height: 16 }
        case 'small':
            return { width: 75, height: 24 }
        case 'medium':
            return { width: 112, height: 36 }
        case 'large':
        default:
            return { width: 150, height: 48 }
    }
})

const textSizeClass = computed(() => {
    switch (props.size) {
        case 'extra-small':
            return 'text-3xl'
        case 'small':
            return 'text-4xl'
        case 'medium':
            return 'text-6xl'
        case 'large':
        default:
            return 'text-8xl'
    }
})
</script>