<script setup>
import Hero from "@/components/Hero.vue";
import HomeCards from "@/components/HomeCards.vue";
import JobListings from "@/components/JobListings.vue";
</script>

<template>
  <Hero title="Find your dream job" subtitle="Never give up on your dreams" />
  <HomeCards />
  <JobListings :limit="3" :showButton="true" />
</template>
