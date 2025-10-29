<template>
  <div>
    <header class="bg-dark p-3">
      <ul class="nav">
        <li class="nav-item"><NuxtLink class="nav-link text-white" to="/">Main</NuxtLink></li>
        <li class="nav-item"><NuxtLink class="nav-link text-white" to="contact">Contact</NuxtLink></li>
        <li class="nav-item"><NuxtLink class="nav-link text-white" to="users">Users</NuxtLink></li>
      </ul>
    </header>

    <div class="container py-5">
        <slot />
    </div>

    <footer class="bg-dark p-3">
        <p class="text-white">Users footer</p>
    </footer>

  </div>
</template>

<style>
header a:not(.router-link-exact-active):hover {
  text-decoration: underline;
}

header a.router-link-exact-active {
  color: rgb(31, 204, 175)!important;
  font-weight: 500;
}
</style>
