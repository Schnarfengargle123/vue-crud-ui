<script setup>
import { RouterLink, RouterView } from 'vue-router';
</script>

<template>
  <div>
    <header>
      <nav>
        <RouterLink to="/dashboard">Dashboard</RouterLink>
        <RouterLink to="/about">About</RouterLink>
        <RouterLink to="/login">Login</RouterLink>
        <RouterLink to="/register">Register</RouterLink>
      </nav>
    </header>

    <RouterView />
  </div>
</template>

<style scoped>
div {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: center;
  /* background: orange; */
  height: 50%;
}

header {
  width: 24rem;
}

nav {
  font-size: large;
  text-align: center;
  margin-top: 2rem;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}
</style>
