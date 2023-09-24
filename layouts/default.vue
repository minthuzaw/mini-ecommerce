<template>
  <div class="bg-gray-100 min-h-screen text-gray-900">
    <Title>{{ title }}</Title>
    <nav class="bg-white shadow text-lg px-3 py-4 mx-auto w-full md:w-1/2 lg:w-1/2">
      <div class="container mx-auto flex items-center justify-between px-6">
        <div>
          <NuxtLink to="/">
            <img src="~/assets/logo.png" alt="Logo" width="30" height="30"/>
          </NuxtLink>
        </div>
        <div>
          <ul class="flex space-x-6 md:space-x-12 lg:space-x-12">
            <li>
              <NuxtLink to="/">Home</NuxtLink>
            </li>
            <li>
              <NuxtLink to="/about">About</NuxtLink>
            </li>
          </ul>
        </div>
      </div>
    </nav>
    <slot/>
  </div>
</template>

<script setup>
const title = useState('title', () => useRuntimeConfig().public.appName)
</script>

<style scoped>
.router-link-active {
  font-weight: bold;
  color: #4484ed;
}
</style>
