<script setup lang="ts">
definePageMeta({
  layout: 'users'
})

interface Userr {
  id: number,
  firstName: string,
  lastName: string
}


const url = 'https://dummyjson.com/users'

const { data } = await useFetch(url);
const users = ref<Userr[]>(data.value.users);

</script>

<template>
  <div>
    <h1>All users</h1>
    <ul class="d-flex list-unstyled gap-3 flex-wrap">
      <li v-for="user in users" :key="user.id">
        <NuxtLink :to="`users/${user.id}`" class="btn btn-dark">{{ user.firstName }}  {{ user.lastName  }}</NuxtLink>
      </li>
    </ul>
  </div>
</template>

<style scoped></style>
