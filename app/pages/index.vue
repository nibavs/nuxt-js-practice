<script setup lang="ts">
import type { Userr } from '~/types/user';

const some = ref<string>('some')

const { data } = await useFetch<{hello: string}>("/api/hello", {
  method: 'post',
  body: {
    first: 'hey',
    second: 'pau'
  }
})




</script>

<template>
  <div>

  <Head>
    <Title>Home page</Title>
    <Meta name="description" content="Home page"/>
  </Head>
    <h1>Home page</h1>
    <p>{{ data?.hello }}</p>


    <p>{{ some }}</p>
  </div>
</template>

<style>
h1 {
  color: red;
}
</style>
