<script setup>
import MainLayout from '../components/MainLayout.vue';
import Contact from '../components/Contact.vue';

// Page Title of Views
const pageTitle = 'Contact'
</script>

<template>
  <MainLayout :pageTitle="pageTitle">
    <section>
      <contact/>
    </section>
  </MainLayout>
</template>