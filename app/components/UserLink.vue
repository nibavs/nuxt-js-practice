<script setup lang="ts">

interface Userr {
    id: number,
    firstName: string,
    lastName: string
}

defineProps<{
    user: Userr
}>();
</script>

<template>
    <NuxtLink :to="`users/${user.id}`" class="btn btn-dark">{{ user.firstName }}  {{ user.lastName  }}</NuxtLink>
</template>

<style scoped>

</style>