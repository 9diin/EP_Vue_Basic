<template>
    <UserName v-model:first-name="first" v-model:last-name="last" />

    <p>Parent FirstName: {{ first }}</p>
    <p>Parent LastName: {{ last }}</p>
</template>

<script setup>
import { ref } from "vue";
import UserName from "./components/ch03/03-48.vue";

const first = ref("John");
const last = ref("Doe");
</script>

<style scoped></style>
