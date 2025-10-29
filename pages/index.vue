<script setup lang="ts">

const some = ref<string>('some')
</script>

<template>
  <div>
    <header>
      <ul>
        <li><NuxtLink to="contact">contact</NuxtLink></li>
        <li><NuxtLink to="users">users</NuxtLink></li>
        <li><NuxtLink to="users/1">user1</NuxtLink></li>
      </ul>
    </header>
    <h1>Main</h1>

    <p>{{ some }}</p>
  </div>
</template>

<style>
h1 {color: red;}
</style>
