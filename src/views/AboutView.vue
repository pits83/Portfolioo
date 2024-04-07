<script setup>
import MainLayout from '../components/MainLayout.vue';
import About from '../components/About.vue';

// Page Title of Views
const pageTitle = 'About'
</script>

<template>
  <MainLayout :pageTitle="pageTitle">
    <section>
      <about/>
    </section>
  </MainLayout>
</template>