<!-- pages/index.vue -->
<template>
  <UContainer>
    <h1 class="text-3xl font-bold mb-6">Our Products</h1>
    <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6">
      <UCard v-for="product in products" :key="product.id">
        <template #header>
          <img :src="product.image" :alt="product.name" class="w-full h-48 object-cover rounded" />
        </template>

        <h2 class="text-xl font-semibold">{{ product.name }}</h2>
        <p class="text-gray-500 mb-2">{{ product.description }}</p>
        <p class="text-lg font-bold text-primary mb-4">${{ product.price }}</p>

        <template #footer>
          <UButton @click="addToCart(product)">Add to Cart</UButton>
        </template>
      </UCard>
    </div>
  </UContainer>
</template>

<script setup>
const products = ref([
  { id: 1, name: 'Product A', description: 'High-quality product A.', price: 29.99, image: 'https://via.placeholder.com/300x200' },
  { id: 2, name: 'Product B', description: 'Stylish and functional product B.', price: 39.99, image: 'https://via.placeholder.com/300x200' },
  { id: 3, name: 'Product C', description: 'Affordable and reliable product C.', price: 19.99, image: 'https://via.placeholder.com/300x200' }
])

function addToCart(product) {
  console.log('Added to cart:', product.name)
}
</script>
