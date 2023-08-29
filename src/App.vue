<template>
  <HomeView />
</template>

<script setup lang="ts">
import { ref } from "vue";
import HomeView from "./views/HomeView.vue";

const msg = ref<string>("World");
</script>
