<template>
  <div v-if="isLoading" class="text-center mt-5">
    Loading ...
  </div>
  <Carousel v-if="!isLoading"/>
  <div class="container mx-auto w-full md:w-1/2 lg:w-1/2 divide-y space-y-8 divide-gray-300">
    <ProductItems v-for="product in items" :key="product.id" :product="product"></ProductItems>
  </div>
</template>

<script setup>
const items = ref()
const isLoading = ref(false)

onMounted(() => {
  fetchApi()
})
const fetchApi = async () => {
  isLoading.value = true
  items.value = await $fetch(useNuxtApp().$apiFetch(`/products?limit=5`))
  isLoading.value = false
}
</script>
