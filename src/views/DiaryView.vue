<script setup>
import MainLayout from '../components/MainLayout.vue';
import Diary from '../components/Diary.vue';



// Page Title of Views
const pageTitle = 'Diary'
</script>


<template>
  <MainLayout :pageTitle="pageTitle">
    
    <!-- Diary -->
    <Diary/>
    
  </MainLayout>
</template>