<template>
  <div class="container mx-auto w-full md:w-1/2 lg:w-1/2 py-8 px-6">
    <Title>{{ product.id }}| {{ title }}</Title>
    <h3 class="text-3xl font-bold">
      <NuxtLink :to="`/products/${product.id}`">
        {{ product.title }}
      </NuxtLink>
    </h3>
    <div class="post-meta text-gray-700 flex items-center space-x-2">
      <div>{{ moment(new Date()).format('ll') }}</div>
      <div>&middot;</div>
      <div>{{ product.id }}</div>
    </div>

    <div class="post-content mt-4">
      {{ product.description }}
    </div>

    <div class="mt-4">
      <NuxtLink to="/" class="bg-blue-700 hover:bg-blue-800 text-white rounded inline-block px-4 py-2">
        Back
      </NuxtLink>
    </div>
  </div>
</template>

<script setup>
import moment from 'moment'

const title = useState('title')
const route = useRoute()

const {data: product} = await useFetch(useNuxtApp().$apiFetch(`/products/${route.params.id}`))

</script>
