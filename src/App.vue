<template>
  <div>
    <NavBar />
    <main class="flex flex-col items-center justify-center min-h-screen pt-20">
      <h1
        class="text-4xl font-bold animate-float-and-color mb-6"
      >
        OpenPlatform
      </h1>
      <div class="space-x-4">
        <button
          @click="fetchData('/')"
          class="bg-blue-500 hover:bg-blue-600 text-white font-semibold py-2 px-4 rounded"
        >
          Fetch /
        </button>
        <button
          @click="fetchData('/hello')"
          class="bg-green-500 hover:bg-green-600 text-white font-semibold py-2 px-4 rounded"
        >
          Fetch /hello
        </button>
        <button
          @click="fetchData('/status')"
          class="bg-purple-500 hover:bg-purple-600 text-white font-semibold py-2 px-4 rounded"
        >
          Fetch /status
        </button>
      </div>
      <p class="mt-6 text-gray-700 text-center" v-if="response">{{ response }}</p>
      <ModulesGrid />
    </main>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import NavBar from './components/NavBar.vue'
import ModulesGrid from './components/ModulesGrid.vue'

const response = ref('')
const backendUrl = import.meta.env.VITE_BACKEND_URL + '/api'

async function fetchData(endpoint) {
  try {
    const url = backendUrl + `${endpoint}`;
    const res = await fetch(url)
    response.value = await res.text()
  } catch (err) {
    response.value = 'Error: ' + err.message
  }
}
</script>

<style scoped>
@keyframes float {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(-10px); }
}
@keyframes color-blend {
  0% { color: #ff0000; }
  25% { color: #00ff00; }
  50% { color: #0000ff; }
  75% { color: #ff00ff; }
  100% { color: #ff0000; }
}

.animate-float-and-color {
  animation: float 3s ease-in-out infinite, color-blend 10s ease-in-out infinite;
}
</style>
