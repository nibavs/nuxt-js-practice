<script setup lang="ts">
import type { Userr } from '~/types/user';


defineProps<{
    user: Userr
}>();
</script>

<template>
    <NuxtLink :to="`users/${user.id}`" class="btn btn-dark">{{ user.firstName }}  {{ user.lastName  }}</NuxtLink>
</template>

<style scoped>

</style>