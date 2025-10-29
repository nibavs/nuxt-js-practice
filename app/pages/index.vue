<script setup lang="ts">
const some = ref<string>('some')
</script>

<template>
  <div>
    <h1>Main</h1>

    <footer>
      <Alert color="primary">
        A simple primary alert—check it out!
      </Alert>
    </footer>

    <p>{{ some }}</p>
  </div>
</template>

<style>
h1 {
  color: red;
}
</style>
