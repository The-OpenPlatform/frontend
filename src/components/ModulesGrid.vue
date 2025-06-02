<script setup>
import { ref, onMounted } from 'vue'

const modules = ref([])

onMounted(async () => {
  const res = await fetch(import.meta.env.VITE_BACKEND_URL + '/api/modules')
  modules.value = await res.json()
})
</script>

<template>
  <div class="grid">
    <h1 class="text-center mt-20">Modules</h1>
    <div v-for="module in modules" :key="module.module_id" class="module">
      <h3>{{ module.name }}</h3>
      <div class="images">
        <img v-for="img in module.images" :key="img.image_id" :src="img.data_url" />
      </div>
    </div>
  </div>
</template>

<style scoped>
.grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
  gap: 1rem;
}
.module {
  border: 1px solid #ccc;
  padding: 1rem;
}
.images img {
  max-width: 100%;
  height: auto;
  display: block;
  margin-top: 0.5rem;
}
</style>