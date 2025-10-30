<script setup lang="ts">
const { user_id } = useRoute().params


definePageMeta({
  layout: 'users'
})


const { data } = await useFetch(`https://dummyjson.com/users/${user_id}`)
</script>


<template>
  <div>
    <h1>User info:</h1>
    <p>{{ data.firstName }} {{ data.lastName }}</p>
  </div>
</template>


<style scoped></style>
