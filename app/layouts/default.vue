<template>
  <div class="min-h-screen bg-white antialiased font-sans">
    <AppNavbar />
    <slot />
    <AppFooter />
  </div>
</template>

<script setup>
import AppNavbar from '~/components/layout/AppNavbar.vue'
import AppFooter from '~/components/layout/AppFooter.vue'
</script>