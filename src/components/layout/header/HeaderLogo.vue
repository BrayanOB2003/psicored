<template>
  <router-link to="/" class="lg:hidden">
    <logo size="extra-small" dark-mode="true"/>
  </router-link>
</template>

<script setup>
import Logo from '@/components/ui/Logo.vue';
import { RouterLink } from 'vue-router'
</script>
