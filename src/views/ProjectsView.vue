<script setup>
import MainLayout from '../components/MainLayout.vue';
import ProjectGallery from '../components/ProjectGallery.vue';



// Page Title of Views
const pageTitle = 'Projects'
</script>


<template>
  <MainLayout :pageTitle="pageTitle">
    
    <!-- Project Gallery -->
    <ProjectGallery />
    
  </MainLayout>
</template>