<script setup>
import logo from '../assets/img/logo.png';
import { RouterLink, useRoute } from 'vue-router';

const isActiveLink = (routePath) => {
  const route = useRoute();
  return route.path === routePath;
}

</script>
<template>
  <nav class="bg-green-700 border-b border-green-500">
    <div class="container mx-auto px-4">
      <div class="flex items-center justify-between h-16">
        <!-- Left side: Logo and title -->
        <div class="flex items-center">
          <img class="h-8 w-auto" :src="logo" alt="Vue Jobs" />
          <span class="hidden md:block text-white text-xl font-bold ml-3">Vue Jobs</span>
        </div>

        <!-- Right side: Navigation links -->
        <div class="flex items-center space-x-4">
          <RouterLink to="/"
            :class="[isActiveLink('/') ? 'bg-green-900' : 'hover:bg-grey-900 hover:text-white', 'text-white', 'px-3', 'py-2', 'rounded-md']">
            Home
          </RouterLink>
          <RouterLink to="/jobs"
            :class="[isActiveLink('/jobs') ? 'bg-green-900' : 'hover:bg-grey-900 hover:text-white', 'text-white', 'px-3', 'py-2', 'rounded-md']">
            Jobs
          </RouterLink>
          <RouterLink to="/jobs/add"
            :class="[isActiveLink('/jobs/add') ? 'bg-green-900' : 'hover:bg-grey-900 hover:text-white', 'text-white', 'px-3', 'py-2', 'rounded-md']">
            Add Job
          </RouterLink>
        </div>
      </div>
    </div>
  </nav>
</template>