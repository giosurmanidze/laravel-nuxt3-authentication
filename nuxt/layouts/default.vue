<script setup lang="ts">
const auth = useAuthStore();


const handleLogout = async() => {
  await auth.logout();
}
</script>

<template>
  <div>
    <button v-if="auth.isLoggedIn" @click="handleLogout">Log out</button>
    <pre>{{ auth.user }}</pre>
    <ul>
      <li><NuxtLink to="/">Home</NuxtLink></li>
      <li><NuxtLink to="/register">Register</NuxtLink></li>
      <li><NuxtLink to="/login">Login</NuxtLink></li>
      <li><NuxtLink to="/auth-only">Auth only</NuxtLink></li>
      <li><NuxtLink to="/guest-only">Guest only</NuxtLink></li>
    </ul>
    <slot />
  </div>
</template>
