<script setup lang="ts">
// import type { Userr } from '~/types/user';

interface Userr {
  id: number,
  firstName: string,
  lastName: string
}

definePageMeta({
  layout: 'users'
})

interface ApiResponse {
  users: Userr[]
}


const url = 'https://dummyjson.com/users'

const { data } = await useFetch<ApiResponse>(url);
const users = ref<Userr[]>(data.value?.users || []);

</script>

<template>
  <div>
    <h1>All users</h1>
    <ul class="d-flex list-unstyled gap-3 flex-wrap">
      <li v-for="user in users" :key="user.id">
        <UserLink :user="user"/>
      </li>
    </ul>
  </div>
</template>

<style scoped></style>
