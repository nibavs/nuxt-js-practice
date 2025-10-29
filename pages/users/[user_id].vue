<template>
    <div>
        <h1>User id: {{ user_id }}</h1>
    </div>
</template>

<script setup lang="ts">
const { user_id } = useRoute().params;
</script>

<style scoped>

</style>