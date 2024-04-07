<script setup>
import MainLayout from '../components/MainLayout.vue';
import HeroBanner from '../components/HeroBanner.vue';


// Page Title of Views
const pageTitle = 'Home'
</script>

<template>
  <MainLayout :pageTitle="pageTitle">
    
    <!-- Hero Banner Section -->
    <HeroBanner />

  </MainLayout>
</template>